# Xóa file cũ và tạo lại
rm subdomain_to_ip.sh
cat > subdomain_to_ip.sh << 'EOF'
#!/bin/bash

echo "[*] Resolving subdomains to IPs..."

while read subdomain; do
    ip=$(dig +short "$subdomain" -t A | head -1)
    if [ -n "$ip" ]; then
        echo "$ip $subdomain"
    fi
done < subdomain_vnpt_final.txt | sort > subdomains_with_ips.txt

echo "[+] Done. Check subdomains_with_ips.txt"
EOF

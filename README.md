
Unofficial Pangolin Helm chart

![Pangolin network in kubernetes](./docs/pangolin-net.png)

```bash
git clone https://github.com/XpaceOff/xo-pangolin.git
cd xo-pangolin

# Install example:
helm install pangolin xo-pangolin \
--set-string settings.pangolin.serverSecretKey=SECRET_KEY_HERE \
--set-string settings.traefik.certificatesResolver.email=YOUR_EMAIL_HERE \
--set-string ingress.hostDomain="YOUR_DOMAIN_HERE" \
--set-string volumes[0].name=vol-pangolin \
--set-string volumes[0].nfs.path=/volume/cluster/pangolin \
--set-string volumes[0].nfs.server=nas.lan \
--set settings.pangolin.email.enabled=true \
--set settings.pangolin.email.smtp_host=nas.lan \
--set settings.pangolin.email.smtp_port=587 \
--set settings.pangolin.email.smtp_user="SMTP_USER_HERE" \
--set settings.pangolin.email.smtp_pass="SMTP_PASS_HERE" \
--set settings.pangolin.email.smtp_tls_reject_unauthorized=false \
--set settings.traefik.proxyProtocol.enabled=true \
--set settings.traefik.proxyProtocol.trustedIPs[0]="10.48.0.0/16" \
--set settings.maxmind.enabled=true \
--set settings.maxmind.id="MAXMIND_ID_HERE" \
--set settings.maxmind.key="MAXMIND_KEY_KERE" \

# Uninstall example:
helm uninstall pangolin
```

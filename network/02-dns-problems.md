# Проблемы DNS (сайты не открываются, но ping 8.8.8.8 работает)

**Шаги:**
1. `nslookup google.com` - DNS‑запрос для получения IP‑адресов домена google.com
2. `ping google.com` (ping - команда проверки доступности узла путем отправления ICMP-пакетов (Internet Control Message Protocol) к целевому узлу и измерения время отклика)
3. Если nslookup работает, а ping — нет, то проблема в hosts-файле

**Команды:**
- Windows: `ipconfig /flushdns` - очищает и сбрасывает содержимое кэша сопоставителя DNS-клиента
- Linux: `sudo systemd-resolve --flush-caches` - используется для очистки локального кэша DNS в системах Linux.

**Решение:**  
Сменить DNS в настройках сети вручную на:
- 8.8.8.8 + 8.8.4.4 (Google)
- или 1.1.1.1 + 1.0.0.1 (Cloudflare)

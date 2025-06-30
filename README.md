import socket

# IP target
target_ip = input("alamat IP target: ")

# Range port 
port_awal = 1
port_akhir = 1024

print(f"Memindai {target_ip} dari port {port_awal} sampai {port_akhir}...\n")

for port in range(port_awal, port_akhir + 1):
    sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    sock.settimeout(0.5)
    hasil = sock.connect_ex((target_ip, port))
    if hasil == 0:
        print(f"Port {port} TERBUKA")
    sock.close()

print("\nPemindaian selesai.")

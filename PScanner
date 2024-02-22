import socket

def scan_ports(target, start_port, end_port):
    print(f'Scanning target {target} for open ports...')
    for port in range(start_port, end_port + 1):
        try:
            sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
            sock.settimeout(1)
            result = sock.connect_ex((target, port))
            if result == 0:
                print(f"Port {port} is open")
            sock.close()
        except KeyboardInterrupt:
            print("\nExiting...")
            break
        except socket.gaierror:
            print("Hostname could not be resolved. Exiting")
            break
        except socket.error:
            print("Couldn't connect to server")
            break

if __name__ == '__main__':
    target = input("Enter target IP address: ")
    start_port = int(input("Enter starting port number: "))
    end_port = int(input("Enter ending port number: "))

    scan_ports(target, start_port, end_port)

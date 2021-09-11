import pyfiglet
import sys
import socket
from datetime import datetime

import target as target

ascii_banner = pyfiglet.figlet_format("imran")
print(ascii_banner)

if len(sys.argv) == 2:
    target = socket.gethostbyname(sys.argv[1])

else:
    print("Invalid amount of Argument you must enter the IP")
print("_" * 5)
print("Scanning target:" + target)
print("Scanning started at:" + str(datetime.now()))
print("_" * 5)

try:
    for port in range(1, 100):
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        socket.setdefaulttimeout(1)

        result = s.connect_ex((target, port))
        if result == 0:
            print("port {} is open".format(port))
        s.close()

except KeyboardInterrupt:
    print("\n Exitting Program !!!!")
    sys.exit()
except socket.gaierror:
    print("\n Hostname Could Not Be Resolved !!!!")
    sys.exit()
except socket.error:
    print("\n Server not responding !!!!")
    sys.exit()

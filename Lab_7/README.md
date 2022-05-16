# Lab 7
## Lab 7A: ThingSpeak

```ssh
$ sudo pip3 install -U psutil
$ cd ~/demo
$ cp ~/iot/lesson7/thingspeak_cpu_loop.py . //did not work
$ cp ~/iot/lesson7/thingspeak_feed.py .
$ cat thingspeak_cpu_loop.py // did not work
$ cat thingspeak_feed.py
$ python3 thingspeak_feed.py
```
![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_7/Lab7/7A1.png)
![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_7/Lab7/7A2.png)
![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_7/Lab7/7A3.png)


## Lab 7B: Google Sheets

```ssh
$ sudo pip3 install -U gspread oauth2client
$ cd demo
$ cp ~/iot/lesson3/system_info.py .
$ cp ~/iot/lesson7/rpi_spreadsheet.py .
$ scp rpidata-*.json pi@192.168.x.xxx:/home/pi/demo
$ nano rpi_spreadsheet.py
$ python3 rpi_spreadsheet.py
```
![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_7/Lab7/7b1.png)
![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_7/Lab7/7b3.png)
![This is an image](https://github.com/rshrest2/CPE322/blob/main/Lab_7/Lab7/7b2.png)

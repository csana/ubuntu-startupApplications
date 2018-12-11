#What is it?

This is my ubuntu startup script, I start my login tasks from here.

#How it works?
Put the mystartuptasks file somewhere. To start it after (graphical) login,
start it via Indítópult:

    Name: MyStartupTasks
    Command:  ~/mystartuptask
    Description: Start my startup jobs...

#What I use?

##Conky
Start my conky configs. You can find it on my github page too...

##LogAlert

It based on https://help.ubuntu.com/community/AudibleLogs:
    tail -f -n1 /var/log/alllogs | awk '/pattern1/{code}/pattern2/&&/pattern3/{code}'

Currently I used it for playing sound when UFW block something:

    tail -f -n1 /var/log/ufw.log | awk '/UFW BLOCK/{system("play -q /usr/share/sounds/gnome/default/alerts/sonar.ogg")}' &


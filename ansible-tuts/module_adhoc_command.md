COPY MOdule
ansible ec2 -m copy -a 'src=./test.txt dest=/home/ansiuser/test.txt owner=ansiuser group=ansiuser mode=0766'

FILE Module
ansible ec2 -m file -a 'path=/home/ansiuser/ansi state=directory mode=0755'

Add Line to text file
ansible ec2 -m lineinfile -a 'path=/home/ansiuser/prod.env line="AGE=30"'

Shell Command remotely
ansible <target-host> -m shell -a 'cat /tmp/repos.json'

module to get data from browser and saved it into target host
ansible ec2 -m uri -a 'url=https://api.github.com/users/raghib1992/repos dest=/tmp/repos.json'
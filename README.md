# greatest-number-of-mail
Write a program to read through the mbox-short.txt and figure out who has sent the greatest number of mail messages. The program looks for 'From ' lines and takes the second word of those lines as the person who sent the mail. The program creates a Python dictionary that maps the sender's mail address to a count of the number of times they appear in the file. After the dictionary is produced, the program reads through the dictionary using a maximum loop to find the most prolific committer.
name = input("Enter file:")
if len(name) < 1 : name = "mbox-short.txt"
handle = open(name)
mail= dict()
lst=list()
for line in handle:
    line=line.rstrip()
    if line.startswith("From "):
      r=line.split()
      lst.append(r[1])
for i in lst:
  mail[i]=mail.get(i,0)+1
max_value=None
max_key=None
for k,v in mail.items():
    if v>max_value:
        max_value=v
        max_key=k
   
print(max_key, max_value)

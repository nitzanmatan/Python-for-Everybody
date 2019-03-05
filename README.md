# Python-for-Everybody'''9.4 Write a program to read through the mbox-short.txt and figure out who has sent the greatest number of mail messages. 
'''The program looks for 'From ' lines and takes the second word of those lines as the person who sent the mail. 
The program creates a Python dictionary that maps the sender's mail address to a count of the number of times they appear in the file. 
After the dictionary is produced, the program reads through the dictionary using a maximum loop to find the most prolific committer.'''


fname = input ('Enter File: ')
hand = open (fname)
#hand = open ('mbox-short.txt')
di= dict()
count = 0
for line in hand:
    line=line.rstrip()
    words=line.split()
    if len(words)< 3 or words[0]!='From' : continue
    email = words[1]
    di[email] = di.get (email,0)+1
largest = 0
theword = None
for k,v in di.items():
    if v > largest :
        largest = v
        theword = k
    largest = max (v,largest)
print (theword,largest)



    


    
    

   
  

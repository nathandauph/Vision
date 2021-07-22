#! /usr/bin/env python3
import os
import re
import sys
import csv
import operator
import collections
import pandas
import yaml
import unidecode
from colorama import Fore, Back, Style
#insert ascii art here 
#print("""\
#""")
#Import a file.
filename= input('Enter file name: ')
#Open and read file.
df=pandas.read_csv(filename)
pandas.set_option('display.max_rows', None)
dest_col_lst=df['Destination'].tolist()
count_dest_list=collections.Counter(dest_col_lst)
src_col_lst=df['Source'].tolist()
count_src_list=collections.Counter(src_col_lst)
countedlst= count_dest_list + count_src_list
print('loading file please wait')
lst=[]
print("""
                VVVVVVVV           VVVVVVVV iiii                     iiii                                     
                V::::::V           V::::::Vi::::i                   i::::i                                    
                V::::::V           V::::::V iiii                     iiii                                     
                V::::::V           V::::::V                                                                   
                 V:::::V           V:::::Viiiiiii     ssssssssss   iiiiiii    ooooooooooo   nnnn  nnnnnnnn    
                  V:::::V         V:::::V i:::::i   ss::::::::::s  i:::::i  oo:::::::::::oo n:::nn::::::::nn  
                   V:::::V       V:::::V   i::::i ss:::::::::::::s  i::::i o:::::::::::::::on::::::::::::::nn 
                    V:::::V     V:::::V    i::::i s::::::ssss:::::s i::::i o:::::ooooo:::::onn:::::::::::::::n
                     V:::::V   V:::::V     i::::i  s:::::s  ssssss  i::::i o::::o     o::::o  n:::::nnnn:::::n
                      V:::::V V:::::V      i::::i    s::::::s       i::::i o::::o     o::::o  n::::n    n::::n
                       V:::::V:::::V       i::::i       s::::::s    i::::i o::::o     o::::o  n::::n    n::::n
                        V:::::::::V        i::::i ssssss   s:::::s  i::::i o::::o     o::::o  n::::n    n::::n
                         V:::::::V        i::::::is:::::ssss::::::si::::::io:::::ooooo:::::o  n::::n    n::::n
                          V:::::V         i::::::is::::::::::::::s i::::::io:::::::::::::::o  n::::n    n::::n
                           V:::V          i::::::i s:::::::::::ss  i::::::i oo:::::::::::oo   n::::n    n::::n
                            VVV           iiiiiiii  sssssssssss    iiiiiiii   ooooooooooo     nnnnnn    nnnnnn
                                                    *--------------------------------*
                                                    *                                *
                                                    *   This is vision. A program    *
                                                    *          created by:           *
                                                    *                                *
                                                    *             NATE B             *
                                                    *               &                *
                                                    *             NATE D             *
                                                    *                                *
                                                    *--------------------------------*
"""
)
while True:
    print(
    ("\n+-------------------------------------------------------------------------------------------------------------------+"),
    ('\nWelcome to Vision. What information would you like to see?' + Fore.RESET),
    ("\n+-------------------------------------------------------------------------------------------------------------------+"),
    ('\n[1]'),('='),(Fore.YELLOW + '(List ALL IPs)' + Fore.RESET),(' lists all ip addresses that were involved in the network capture.'),
    ('\n[2]'),('='),(Fore.YELLOW + '(Most Frequent IP)' + Fore.RESET),('lists the ip address that appears the most in the network capture.'),
    ('\n[3]'),('='),(Fore.YELLOW + '(Least Frequent IP)' + Fore.RESET),('lists the ip address that appears the least in the network capture.'),
    ('\n[4]'),('='),(Fore.YELLOW + '(Source IP)' + Fore.RESET),('lists all ip addresses that network traffic originated.'),
    ('\n[5]'),('='),(Fore.YELLOW + '(Destination IP)' + Fore.RESET),('lists all ip addresses that network traffic was sent to.'),
    ('\n[6]'),('='),(Fore.YELLOW + '(Most Frequent Source IP)' + Fore.RESET),('lists the most frquent ip traffic origin.'),
    ('\n[7]'),('='),(Fore.YELLOW + '(Most Frequent Destination IP)' + Fore.RESET),('lists the most frequent ip address where traffic ended.'),
    ('\n[8]'),('='),(Fore.YELLOW + '(Least Frequent Source IP)' + Fore.RESET),('lists the source ip that occured the least'),
    ('\n[9]'),('='),(Fore.YELLOW + '(Least Frequent Destination IP)' + Fore.RESET),('lists the destination ip that occured the least'),
    ("\n+-------------------------------------------------------------------------------------------------------------------+"),
    )
    userselection= input('What information would you like? ')
#if list is selected then list all of the ips that are in the log file and the amount of times the appear
    if userselection == '1':
        print('\n'+yaml.dump(countedlst, sort_keys=False, default_flow_style=False))
        continue
#if the user inputs 'most' distplay the most common ip address
    if userselection == '2':
        print('\n\n\n'+'Most Frequent IP is: '+max(countedlst.items(), key=operator.itemgetter(1))[0]+'\n\n\n')    
    if userselection == '3':
        print('\n\n\n'+'Least Frequent IP is :'+min(countedlst, key=lambda k: countedlst[k])+'\n\n\n')
    if userselection == '5':
        print(yaml.dump(count_dest_list, sort_keys=False, default_flow_style=False))  
    if userselection == '4':
        print(yaml.dump(count_src_list, sort_keys=False, default_flow_style=False))
    if userselection == '7':
        print('\n\n\n'+'Most Frequent Destination IP is: '+max(count_dest_list.items(), key=operator.itemgetter(1))[0]+'\n\n\n')   
    if userselection == '6':
        print('\n\n\n'+'Most Frequent Source IP is: '+max(count_src_list.items(), key=operator.itemgetter(1))[0]+'\n\n\n')
    if userselection == '8':
        print('\n\n\n'+'Least Frequent Source IP is:'+min(count_src_list, key=lambda k: countedlst[k])+'\n\n\n')
    if userselection == '9':
        print('\n\n\n'+'Least Frequent Destination IP is: '+min(count_dest_list, key=lambda k: countedlst[k])+'\n\n\n')

<p align="center">
  <img src="https://i.imgur.com/ElWjENc.png" alt="Google Logo" width="200" height="200" />
</p>

> **Disclaimer**: This documentation pertains to a **fictional** organization and is part of a lab exercise in the Google Cybersecurity Program. All the data and scenarios presented here are purely fictitious and for educational purposes only.


# IP-Allowlist-Updater

## Project Description

At my organization, access to restricted content is controlled with an allowlist of IP addresses. The purpose of this repository is to automate the update of the `allow_list.txt` file by removing the IP addresses which should no longer have access based on the remove list.

# How it Works:

Open the File that Contains the Allow List

For the first part of the algorithm, I opened the allow_list.txt file. First, I assigned this file name as a string to the import_file variable:

```python
# Assign 'import_file' to the name of the file

import_file = "allow_list.txt

Then, I used a with statement to open the file:

#Build 'with' statement to read in the initial contents of the file

with open(import_file, "r") as file:
```

## Read the File Contents

In order to read the file contents, I used the .read() method to convert it into a string:
```python
with open(import_file, "r") as file:

  # Use '.read()' to read the imported file and store it in a variable named 'ip_addresses'

ip_addresses = file.read()
```

# Convert the String into a List

To remove individual IP addresses from the allow list, I converted the ip_addresses string into a list:

```python
# Use '.split' to convert 'ip-addresses' from a string to a list

ip_addresses = ip_addresses.split()
```

# Iterate through the Remove List
A key part of my algorithm involves iterating through the IP addresses that are elements in the remove_list:
```python
# Build iterative statement 
# Name loop variable 'element'
# Loop through 'remove_list'
```
# Remove IP Addresses that are on the Remove List

My algorithm requires removing any IP address from the ip_addresses list that is also contained in remove_list:

```python
if element in remove_list:

# Create conditional statement to evaluate if 'element' is in 'ip_addresses'

if element in ip_addresses:

# use the '.remove()' method to remove
#elements from 'ip_addresses'

    ip_addresses.remove(element)
```
# Update the File with the Revised List of IP Addresses
As a final step in my algorithm, I needed to update the allow list file with the revised list of IP addresses:
```python
ip_addresses = "\n".join(ip_addresses)

with open(import_file, "w") as file:
    file.write(ip_addresses)
```

# Summary
I created an algorithm that removes IP addresses identified in a remove_list variable from the allow_list.txt file of approved IP addresses. This algorithm involved opening the file, converting it to a string to be read, and then converting this string to a list stored in the variable ip_addresses. I then iterated through the IP addresses in remove_list, removing the element from ip_addresses if it was present. After this, I used the .join() method to convert ip_addresses back into a string so that I could write over the contents of the allow_list.txt file with the revised list of IP addresses.


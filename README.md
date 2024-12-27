#contactbook
2
#Initialization:

contacts = {}

#structure:
while True: 
     print('\nContact Book App')
     print('1. Create Contact')
     print('2. View Contact')  
     print('3. Update Contm act')  
     print('4. Delete Contact')  
     print('5. Search Contact')  
     print('6. Count Contacts')  
     print('7. Exit')

     choice = input('Enter your choice = ')

#create contact:
     if choice == '1':
         name = input('Enter your name = ')
         if name in contacts:
             print(f'Contact name {name} already exists!')
         else:  
             age = input('Enter age= ')
             email = input('Enter email= ')
             mobile = input('Enter mobile number= ')
             contacts[name] = {'age': int(age), 'email': email, 'mobile': mobile}
             print(f'Contact name {name} has been created successfully!')
#view contact:
     elif choice == '2':
         name = input('Enter contact name to view= ')
         if name in contacts:
             contact = contacts[name]
             print(f'Name: {name}, Age: {contact["age"]}, Mobile: {contact["mobile"]}, Email: {contact["email"]}')
         else:  
             print('Contact not found!')
#update contacts:
     elif choice == '3':
         name = input('Enter name to update contact= ')
         if name in contacts:
             age = input('Enter updated age= ')
             email = input('Enter updated email= ')
             mobile = input('Enter updated mobile number= ')
             contacts[name] = {'age': int(age), 'email': email, 'mobile': mobile}
             print(f'Contact name {name} has been updated successfully!')
         else:  
             print('Contact not found!')
#delete contact:
     elif choice == '4':
         name = input('Enter contact name to delete: ')
         if name in contacts:
             del contacts[name]
             print(f'Contact name {name} has been deleted successfully!')
         else:
             print('Contact not found!')
#search contect:
     elif choice == '5':
         search_name = input('Enter contact name to search= ')
         found = False
         for name, contact in contacts.items():
             if search_name.lower() in name.lower():
                 print(f'Found - Name: {name}, Age: {contact["age"]}, Mobile: {contact["mobile"]}, Email: {contact["email"]}')
                 found = True
         if not found:
             print('No contact with this name found!') 
#count contacts:
     elif choice == '6':
         print(f'Total contacts in your book= {len(contacts)}')
#exit:
     elif choice == '7':
         print('Bye, have a nice day... chal nikal')
         break
#invalid input:        
     else:
         print('sahi input daal bey!')

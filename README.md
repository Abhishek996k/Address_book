# Address_book
int choice = scanner.nextInt();
        scanner.nextLine(); // Consume the newline

        switch (choice) {
            case 1:
                System.out.print("Enter the name: ");
                String name = scanner.nextLine();
                System.out.print("Enter the mobile number: ");
                String mobilenumber = scanner.nextLine();
                System.out.print("Enter email id: ");
                String emailid = scanner.nextLine();

                Contacts newContact = new Contacts(name, mobilenumber, emailid);
                alldetails.addContact(newContact);
                System.out.println("Contact added successfully.");
                 System.out.println();
                break;

            case 2:
                System.out.print("Enter the name of the contact to remove: ");
                String contactToRemove = scanner.nextLine();
                Contacts deletedContact = alldetails.searchContact(contactToRemove);
                if (deletedContact != null) {
                    alldetails.deleteContact(deletedContact);
                    System.out.println("Contact removed successfully.");
                    System.out.println();
                } else {
                    System.out.println("Contact not found.");
                     System.out.println();
                }
                break;

            case 3:
                System.out.print("Enter the name of the contact to search: ");
                String contactToSearch = scanner.nextLine();
                Contacts contactfound = alldetails.searchContact(contactToSearch);
                if (contactfound != null) {
                    System.out.println("Contact has been found: " + contactfound);
                } else {
                    System.out.println("Contact not found.");
                     System.out.println();
                }
                break;

            case 4:
                ArrayList<Contacts> allContacts = alldetails.AllContacts();
                if (!allContacts.isEmpty()) {
                    System.out.println("All Contacts:");
                     System.out.println();
                    for (Contacts contact : allContacts) {
                        System.out.println(contact);
                    }
                } else {
                    System.out.println("No contacts found in the address book.");
                }
                break;

            case 5:
                System.out.println("Exit!!");
                System.exit(0);
                break;

            default:
                System.out.println("Incorrect choice. Please select a valid option.");
        }
}

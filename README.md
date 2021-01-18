# Social-Network
A social network similar to Facebook, Instagram, Twitter and LinkedIn.  The system will include the following services: Authentication service, Identity service, Social service and Notification service.

using System;

namespace ConsoleApp2
{
    class Program
    {
        static void Main(string[] args)
        {
            NewUser User1 = new NewUser();
            Console.WriteLine("Enter UserName");
            User1.Name = Console.ReadLine();
            Console.WriteLine("Enter new Password");
            User1.Password = Console.ReadLine();

            Console.ReadLine();
        }
    }

    class NewUser
    {
        private string name;
        private string password;
        int i = 0;
        public string Name
        {
            set { name = value; }
            get { return name; }
        }

        public string Password
        {

            set
            {
                int digit = 0, upper = 0, lower = 0;
                bool  ok = false;
                do
                {
                    if (value.Length < 8 || value.Length > 16)
                    {
                        Console.WriteLine("password must be between 8-16 digits " +
                            "enter again");
                        value = Console.ReadLine();
                    }

                    else
                        ok = true;

                } while (!ok);

                
                foreach (char i in value)
                {
                    if ((int)i >= 97 && (int)i <= 122)
                    { lower = 1; }
                    else if ((int)i >= 65 && (int)i <= 90)
                    { upper = 1; }
                    else if ((int)i >= 48 && (int)i <= 57)
                    { digit = 1; }
                }
                if (lower == 1 && upper == 1 && digit == 1)
                    password = value;
                else
                    Console.WriteLine("password must be have numbers and letters " +
                        "with big and small letter");

            }
            get { return password; }
        }
    }
}

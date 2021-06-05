# Employee details without duplicates and file handling

Here I have writen a code for Employee details. In this program first it will give the options like

1.create

2.display

3.RaiseSalary

4.Exit

If we create option thn again it will give the options like

1.Clerk

2.Manager

3.Programmer

4.Exit

If we select Clerk it will ask to enter the employee name and age to the user. Here deciding salary and raising salary is not in the user hand. This is same for Manager and Programmer and each one have different salary. If we choose option 4 it will exit and go back to pervious menu.

Once the employee details are created then duplicates are not allowed. That means if we try to enter the records of same employee then it will not accept it.

If we choose display then it will display the employee datails. 

If we choose RaiseSalary the the slary will be raised to everyone according to thier designation.

If we choose exit then it will terminate the execution.

Here I have created 5 classes. Employee class is common for all it contains the business logic.

    String name, desig;
		int age, sal;
    
These are the datamembers of the employee class.

      BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
			System.out.print("\n Enter Name ");
			name = br.readLine();
			System.out.print("\nEnter Age : ");
			age = Integer.parseInt(br.readLine());
      
Here I used try and catch block to enter the name and age of the employees and BufferReader to enter the employee data. 

The clerk class is final class and it extends employee class. This class is final because nobody can change the salary here.

     public Clerk() 
		{
			desig = "Clerk";
			sal = 3000;
		}
		public void raiseSalary() 
		{
			sal += 10000;
		}
    
 The methods are used in Manager and Programmer class also.
 
Here I am creating the file object and storing the data in the file permanently in the device. 
 
    File file = new File("C:/Users/VEERU/Desktop/textfile/Employee2_details.txt");
		file.createNewFile();
		PrintWriter writer = new PrintWriter(new FileOutputStream(file,true));
    
 And used switch case to choose the optionns according to the user need.   
 
     case 1: emp = new Clerk();
     break;
     case 2: emp = new Manager();
     break;
     case 3: emp = new Programmer();
     break;
     case 4: break;
     default: System.out.print("\n\ninvalid entry...!");
     break;	
     
This for loop is used to check if the employee details are already exist or not. If present then it will print record already exist as output.    
     
     for( Employee k : employee) 
     {
	if(k.name.equals(emp.name) && k.age == emp.age) 
	  {
	    System.out.print("\nRecord already exists...");
	    existing = true;
	    break;
	  }
      }
      
I have used try catch block to handle the exceptions.      

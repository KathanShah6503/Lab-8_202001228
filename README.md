# Name: Kathan Shah
# ID: 202001228

# Lab1_202001228 

# Lab Exercises

###Q1

##Functional Requirements

	1. Authentication (Student/Member/Library staff/Librarian Login)
	2. Should show list of books available to borrow.
	3. Record of books borrowed by the user.
	4. Authorization Levels
		- Librarian(Admin)
			- Complete control over the system
		- Library Staff
			- Handling day-to-day book transactions
		- Members
			- Get information about available books and borrowed books
		- Non-member
			- Can search/browse books online but can't borrow/issue.
	5. A Web aaplication using HTML 5.
	6. Information should be encrypted.
	7. From the list of available books, a user should easily borrow a book.
	8. If a book has been borrowed by a user, it should allow the user to easily return it.
	9. Information about a book like author name, genre, publisher name.
	10. For every new entry of the book, A unique and specific call no. and barcode should be generated.
	11. The website should only be accesible via the institute's LAN.
	12. Features like "Change Password", "Reading History", "Search History" should be made available.
	13. The system should allow a user to re-issue a book gievn that no user is willing to borrow/issue it.
	14. If a user fails to return the book before the due date, he/she should be fined.
	15. If a book is not available, a user can ask library system to purchase it through the system.
	16. A user should be able to search books by entering author name or publisher name or any keyword or call no. or the barcode of the book.
	17. If a user has not logged in the system, he should not be able to issue or return any book.
	
##Non-Functional Requirements

	1. The system should be fast enough so that when a user searches for a book, it should immediately show the results.
	2. If a user borrows a book or returns a book, it should immediately reflect in the system.
	3. When a user issues or returns a book, he should be getting a email regarding the same.
	4. The system should remind the user to return the book sending a mail prior to 1 or 2 days before the deadline.
	5. When the requested book is available, the user should be notified.
	6. The system should be accesible even though large no. of users are using it at the same time.
	

###Q2

##Scope

	1. The scope of the application is to target approximately 5% of the world population(Approx 466 million people) suffers from disabling hearing loss.
	2. The application is set out to be a impactful solution for for this community that addresses their everyday needs.
	3. The app is optimized for android with low-latency so that it works in real-time.
	
##Features

	1. A alert/vibrate to recognize sounds like car horns or babies.
	2. A real-time speech-to-text convertor to show words that are spoken by other people.
	3. The log is updated in the real-time.
	
##Non-Functional Aspects

	1. Security
		- The information about the user should not be leaked/revealed.
	2. Scalability
		- The app should work fine even though there are many users active at the same time.
	3. Performance/Reliability
		- There should not be any lag in the system.

# Lab5_202001228
![image](https://user-images.githubusercontent.com/75673132/225581033-68e35a4d-e4e5-49f4-8c73-c988d71c244c.png)

I have analyzed 3 files from various github repositories. Here is the explanation of the errors I found.
	
	1. Practical-Python
	--> This file had no errors.

	2. Captcha-Generator.py
	--> As per shown in the image, this file has two errors but there are not really any errors as the error was because of the file missing since we have only checked one file.

	3. Python-mini-project.py
	--> This file has two error of not including library.

# Lab-8_202001228

# Lab Exercises

## 1.
![image](https://user-images.githubusercontent.com/75673132/233319392-2510ae04-f868-4289-ac1c-ac5004a6639a.png)

## 3.

```
import org.junit.Test;
import static org.junit.Assert.*;

public class BoaTest {
    
    @Test
    public void testIsHealthy() {
        Boa boa1 = new Boa("Sneaky", 6, "granola bars");
        assertTrue(boa1.isHealthy());
        
        Boa boa2 = new Boa("Slithery", 8, "pizza");
        assertFalse(boa2.isHealthy());
    }
    
    @Test
    public void testFitsInCage() {
        Boa boa1 = new Boa("Slinky", 4, "mice");
        assertTrue(boa1.fitsInCage(5));
        assertFalse(boa1.fitsInCage(3));
        
        Boa boa2 = new Boa("Curly", 10, "rabbits");
        assertTrue(boa2.fitsInCage(12));
        assertFalse(boa2.fitsInCage(9));
    }
}
```

In the first test case, I am testing the isHealthy method of the Boa class. I created two Boa objects with different favorite foods, and verify that isHealthy returns true for the first object and false for the second object.

In the second test case, I am testing the fitsInCage method of the Boa class. I created two Boa objects with different lengths, and test whether they fit in cages of different lengths. 

(Expect the first boa to fit in a cage of length 5 but not 3, and the second boa to fit in a cage of length 12 but not 9.)

## 4.
```
import org.junit.Before;
import org.junit.Test;
import static org.junit.Assert.*;

public class BoaTest {
    
    private Boa jen;
    private Boa ken;
    
    @Before
    public void setUp() throws Exception {
        jen = new Boa("Jennifer", 2, "grapes");
        ken = new Boa("Kenneth", 3, "granola bars");
    }
    
    @Test
    public void testIsHealthy() {
        assertFalse(jen.isHealthy());
        assertTrue(ken.isHealthy());
    }
    
    @Test
    public void testFitsInCage() {
        assertTrue(jen.fitsInCage(3));
        assertFalse(ken.fitsInCage(2));
    }
}
```

Added private fields for jen and ken to the BoaTest class, and initialized them in the setUp method. I also updated the testIsHealthy and testFitsInCage methods to use these Boa objects for testing.

Note that the setUp method will be executed before each test method, so any changes made to the Boa objects during a test will not affect the objects used in other tests.

## 5.
![image](https://user-images.githubusercontent.com/75673132/233323702-8c2321d5-e640-4981-8854-e6a46e19c445.png)


### testIsHealthy() method

```
import org.junit.Before;
import org.junit.Test;
import static org.junit.Assert.*;

public class BoaTest {
    
    private Boa jen;
    private Boa ken;
    
    @Before
    public void setUp() throws Exception {
        jen = new Boa("Jennifer", 2, "grapes");
        ken = new Boa("Kenneth", 3, "granola bars");
    }
    
    @Test
    public void testIsHealthy() {
        assertFalse(jen.isHealthy());
        assertTrue(ken.isHealthy());
    }
    
    @Test
    public void testFitsInCage() {
        assertTrue(jen.fitsInCage(4));
        assertFalse(ken.fitsInCage(2));
    }
}
```
Added assertions to the testIsHealthy method to check that the isHealthy method returns true for both Boa objects. We also added assertions to the testFitsInCage method to check that the fitsInCage method returns the expected results for the Boa objects.

### testFitsInCage() method


```
import org.junit.Before;
import org.junit.Test;
import static org.junit.Assert.*;

public class BoaTest {
    
    private Boa jen;
    private Boa ken;
    
    @Before
    public void setUp() throws Exception {
        jen = new Boa("Jennifer", 2, "grapes");
        ken = new Boa("Kenneth", 3, "granola bars");
    }
    
    @Test
    public void testIsHealthy() {
        assertFalse(jen.isHealthy());
        assertTrue(ken.isHealthy());
    }
    
    @Test
    public void testFitsInCage() {
        assertFalse(jen.fitsInCage(1)); // cage length less than boa length
        assertFalse(jen.fitsInCage(2)); // cage length equal to boa length
        assertTrue(jen.fitsInCage(3)); // cage length greater than boa length
        
        assertFalse(ken.fitsInCage(2)); // cage length less than boa length
        assertFalse(ken.fitsInCage(3)); // cage length equal to boa length
        assertTrue(ken.fitsInCage(4)); // cage length greater than boa length
    }
}
```
Added assertions to the testFitsInCage method to check that the fitsInCage method returns the expected results for both jen and ken when the cage length is less than, equal to, and greater than the length of the boa.

Note that the testFitsInCage method is now more robust, as it checks the behavior of the fitsInCage method for different input values.

## 6.
![image](https://user-images.githubusercontent.com/75673132/233329358-eeab2ac7-3850-400c-bfb5-bc90679aa9d1.png)

## 7.
![image](https://user-images.githubusercontent.com/75673132/233329548-4c4f604e-621e-4e72-866a-cfa338bae215.png)

The updated code for the Boa class with the new lengthInInches() method:
```
public class Boa {
    private String name;
    private int length; // the length of the boa, in feet
    private String favoriteFood;

    public Boa(String name, int length, String favoriteFood) {
        this.name = name;
        this.length = length;
        this.favoriteFood = favoriteFood;
    }

    // returns true if this boa constrictor is healthy
    public boolean isHealthy() {
        return this.favoriteFood.equals("granola bars");
    }

    // returns true if the length of this boa constrictor is
    // less than the given cage length
    public boolean fitsInCage(int cageLength) {
        return this.length < cageLength;
    }

    // produces the length of the Boa in inches
    public int lengthInInches() {
        return this.length * 12;
    }
}
```

The updated code for the BoaTest class with the new testLengthInInches() method:

```
import static org.junit.Assert.*;
import org.junit.Before;
import org.junit.Test;

public class BoaTest {
    private Boa jen;
    private Boa ken;

    @Before
    public void setUp() throws Exception {
        jen = new Boa("Jennifer", 2, "grapes");
        ken = new Boa("Kenneth", 3, "granola bars");
    }

    @Test
    public void testIsHealthy() {
        assertFalse(jen.isHealthy());
        assertTrue(ken.isHealthy());
    }

    @Test
    public void testFitsInCage() {
        assertTrue(jen.fitsInCage(4));
        assertFalse(jen.fitsInCage(2));
        assertTrue(ken.fitsInCage(6));
        assertTrue(ken.fitsInCage(4));
        assertFalse(ken.fitsInCage(3));
    }

    @Test
    public void testLengthInInches() {
        assertEquals(24, jen.lengthInInches());
        assertEquals(36, ken.lengthInInches());
    }
}
```

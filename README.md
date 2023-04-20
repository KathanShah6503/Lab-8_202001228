# Name: Kathan Shah
# ID: 202001228

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

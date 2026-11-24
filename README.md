## JAVA FRAMEWORKS

### Web-Based Sprint Inventory Application

You are working for a company that licenses and customizes a software application to keep track of inventory in stores. Your job as a software developer is to customize this application to meet a specific customer’s needs. You will choose any type of customer you would like, but it must sell a product composed of parts. An example of products versus parts would be a customer that’s a bicycle shop: a bicycle is a product, and a set of two matching wheels is a part (do not use the bicycle shop example in your project)
***
* A. Create your subgroup and project by logging into GitLab using the web link provided and using the “GitLab How-To” web link, and do the following:

    Clone the project to the IDE.
Commit with a message and push when you complete each of the tasks listed below (e.g., parts C to J).
    >Note: You may commit and push whenever you want to back up your changes, even if a task is not complete.
Submit a copy of the Git repository URL and a copy of the repository branch history retrieved from your repository, which must include the commit messages and dates.

    >Note: Wait until you have completed all the following prompts before you create your copy of the repository branch history. 

* B. Create a README file that includes notes describing where in the code to find the changes you made for each of parts C to J. Each note should include the prompt, file name, line number, and change.

* C. Customize the HTML user interface for your customer’s application. The user interface should include the shop name, the product names, and the names of the parts.

    >Note: Do not remove any elements that were included in the screen. You may add any additional elements you would like or any images, colors, and styles, although it is not required.
    
  **_CHANGES_**: In templates/mainscreen.html Line 14 changed From "My shop" to "CosmoLink" and line 19 changed to "shop" to "CosmoLink Shop"


* D. Add an “About” page to the application to describe your chosen customer’s company to web viewers and include navigation to and from the “About” page and the main screen.

  **_CHANGES_**: Created about.html file under templates and added mainscreen link, in MainScreenControllerr.java line 55 added controller for about page, in mainscreen.html line 20 added link to about page called "About CosmoLink's Mission"


* E. Add a sample inventory appropriate for your chosen store to the application. You should have five parts and five products in your sample inventory and should not overwrite existing data in the database.

    >Note: Wait until you have completed all the following prompts before you create your copy of the repository branch history.

    >Note: Make sure the sample inventory is added only when both the part and product lists are empty. When adding the sample inventory appropriate for the store, the inventory is stored in a set so duplicate items cannot be added to your products. When duplicate items are added, make a “multi-pack” part.
  
  **_CHANGES_**: In BootStrapData.java on line 43-94 added 3 Inhousepart ( sat dish, sat modem, Router) and 2 OutsourcedPart(Power supply and ethernet cable). Also added 5 products (standard,business,ENT,remote and Mobile) packages


* F. Add a “Buy Now” button to your product list. Your “Buy Now” button must meet each of the following parameters:
The “Buy Now” button must be next to the buttons that update and delete products.
The button should decrement the inventory of that product by one. It should not affect the inventory of any of the associated parts.
Display a message that indicates the success or failure of a purchase.

  **_CHANGES_**: Added a "Buy Now" form to mainscreen.html on line 89 and created BuyProductController.java to decrement inventory by 1 and redirect to new purchasesuccess.html/purchaseerror.html templates showing the result.


* G. Modify the parts to track maximum and minimum inventory by doing the following:

    >- Add additional fields to the part entity for maximum and minimum inventory. 
    >- Modify the sample inventory to include the maximum and minimum fields.
    >- Add to the InhousePartForm and OutsourcedPartForm forms additional text inputs for the inventory so the user can set the maximum and minimum values.
    >- Rename the file the persistent storage is saved to.
    >  - Modify the code to enforce that the inventory is between or at the minimum and maximum value.
  
  **_CHANGES_**: Added minInv/maxInv fields to Part.java, showing as new columns on mainscreen.html and added matching input fields to both part form templates. Updated BootStrapData.java with min/max values and renamed the database file in application.properties woth Course and studentID.


* H. Add validation for between or at the maximum and minimum fields. The validation must include the following:
    
    >- Display error messages for low inventory when adding and updating parts if the inventory is less than the minimum number of parts.
    >- Display error messages for low inventory when adding and updating products lowers the part inventory below the minimum.
    >- Display error messages when adding and updating parts if the inventory is greater than the maximum.

  **_CHANGES_**: In AddInhousePartController.java and AddOutsourcedPartController.java i added checks with a specific error message when inventory is below minInv or above maxInv.


* I. Add at least two unit tests for the maximum and minimum fields to the PartTest class in the test package.

  **_CHANGES_**: In PartTest.java on lines 104-119, added getMinInv() and getMaxInv() tests.


* J. Remove the class files for any unused validators in order to clean your code.
  **_CHANGES_**: Reviewed all three validatiors (ValidDeletePart, ValidEnufParts, ValidProductPrice), All three are activley being applied.

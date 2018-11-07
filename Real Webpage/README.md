# Git-Practice-Ch2
This repository is used to teach students command line git with the following exercises. Page numbers reference the book Learn Version Control with Git by Tobias Günther. Project material is from <i>HTML5 and CSS5, 2nd Ed</i> by Sasha Vodnik and can be downloaded from the <a href="http://www.cengage.com/cgi-wadsworth/course_products_wp.pl?fid=M20b&product_isbn_issn=9781305394049">Cengage Book Companion Site</a>.

### Exercise 2-1
1. Create a folder called Git_Ch2 and navigate to the folder in Terminal.app.
2. Run the "git clone" command on p 28 to copy the repository at https://github.com/CS-STech/Git-Practice-Ch2. to your Git_Ch2 folder.
3. Navigate into the new folder created.
4. Open index.html in a web browser. Notice that there are no stylization or photos on the webpage. We will be fixing that in this chapter's assignments.
5. Download styles.css. Preview the document and move it into this project folder.
6. Reload index.html. Notice there is now stylization, but no photos. Before we commit our style sheet, we should add some images to check that the stylization is correct. Because we are not confident that our styles.css fixes our problem, we should stash it so we can commit some images.
7. Use "git add" command to add the style sheet to the log.
8. Use the "git stash" command to temporarily save the working directory. 
9. Run the "git stash list" command to see what Stashes you have.
10. Open index.html. Replace the contents on line 22 with  ```<h1><img src="images/lakeland.gif" width="659" height="165" alt="Lakeland Reeds Bed and Breakfast"></h1>```
11. Reload index.html. Notice that an image is now in place of the company title.
12. Commit the changes with an appropriate message.

### Exercise 2-2
In this assignment, we are going to add some stylization for the Lakeland Reeds website. Since we are adding a new feature to our website, we should create a branch until we can confirm the style sheet functions properly. The book talks about how to create a new branch without anything in the status. For this assignment, we will use a new command to copy the contents of our Stash from Exercise 2-1 to create a branch.

1. Navigate to the Git_Ch2 project folder in Terminal.app.
2. Run "git stash list" to determine the proper identifier for our desired Stash.
3. Run "git stash branch add-stylesheet stash@{0}" to create and switch to a branch called "add-stylesheet".
4. Commit styles.css with an appropriate message.
5. Open styles.css and add the following items:
    * Replace line 14 with 
       ```
       a, article, body, div, figcaption, figure, footer, header, h1, h2, h3, img, nav, p {
    * Add the items below on line 19
       ```
       img {
           max-width: 100%;
           height: auto;
           width: auto;
       }
    * Add the item below on line 90 before the closing curly brace ( "}" )
       ```
       background: url("images/lake.jpg");
    * Add the item below on line 97 before the closing curly brace ( "}" )
       ```
       overflow: auto;
    * Add the item below on line 115 after the closing curly brace ( "}" )
       ```
       article p.imagemap {
           text-align: center;
       }
       article p.imagemap img {
           border: 1px solid black;
           max-width: none;
       }
    * Add the item below on line 126
       ```
       article figure {
           max-width: 100%;
           margin-left: 2em;
           float: right;
       }
       article figure.example {
           margin-top: 2em;
       }
       article figcaption {
           text-align: center;
       }
6. Reload index.html. You will notice a new background on the page, but the header image has disappeared. This is because the header image commit happened on the main branch. Run "git log" to see this.
7. Commit the changes to styles.css with an appropriate message.
8. Switch to the master branch and run "git log" to verify that the changes from add-stylesheet did not save to the master.
9. Merge the add-stylesheet branch and the master branch and run "git log" one more time to verify the merge.

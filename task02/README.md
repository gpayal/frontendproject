20 August 2014, Task 02 Requirements
====================================
## 1. Review of forking, cloning and committing repository.
  1. Go to https://github.com/sunil-pandey/frontendproject
  2. Login to Git
  3. Click on Fork
  4. Go to https://github.com/sunilypandey (sunilypandey is demo participants for demo purposes)
  5. See the forked folder has been copied here
  6. Go to frontendproject
  7. Copy the URL to clipboard
  8. Open a command window and go to the folder when the git repository is to be cloned.
  9. git clone <URL from clipboard>
  10. Create final folder.
  11. Inside final folder, create a file of zero size (touch a file).
  12. git add final
  13. git commit -m "final folder created"
  14. git push
  15. Refresh page in browser
  16. See that final folder is added

## 2. Features of README.md

## 3. Make the original repository upstream remote for your local

  Go to frontendproject  

  One time setting:  
  cd frontendproject  
  git remote add upstream https://github.com/sunil-pandey/frontendproject  

  To get updates from the source repository of sunil-pandey  
  git fetch upstream  
  git merge upstream/master master  
  git push  

## 4. Use bootstrap 3 and make grid layout

  Understand the working of Bootstrap 3 grids  
  http://www.helloerik.com/the-subtle-magic-behind-why-the-bootstrap-3-grid-works  

  Grid example:  
  http://getbootstrap.com/examples/grid/  

  Complete the index.html file with following layout  
  Use desktop columns that is col-md-* classes  
  Check with CTRL+SHIFT+M in Firefox  

  <pre>
  +--------------------------------------------------------+
  |  Banner                                                |
  +--------------------------------------------------------+
  +-------------+-----------------------------+------------+
  | Left Bar    |  Main content               | right bar  |
  |             |                             |            |
  |             |                             |            |
  |             |                             |            |
  |             |                             |            |
  |             |                             |            |
  |             |                             |            |
  |             |                             |            |
  |             |                             |            |
  +-------------+-----------------------------+------------+
  +--------------------------------------------------------+
  |  Footer                                                |
  +--------------------------------------------------------+
  +-----------+----------------+-------------+-------------+
  | Section 1 |  Section 2     | Section 3   | Section 4   |
  |           |                |             |             |
  |           |                |             |             |
  |           |                |             |             |
  |           |                |             |             |
  |           |                |             |             |
  +-----------+----------------+-------------+-------------+
  </pre>

  The content of each box shall be as follows:  
  (replace [[Some Text]] with actual name given in the boxes above)  

  <h4>[[Some Text]]</h4>  
  <p>
  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec a diam lectus. Sed sit amet ipsum mauris. Maecenas congue ligula ac quam viverra nec consectetur ante hendrerit. Donec et mollis dolor. Praesent et diam eget libero egestas mattis sit amet vitae augue. Nam tincidunt congue enim, ut porta lorem lacinia consectetur. Donec ut libero sed arcu vehicula ultricies a non tortor. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean ut gravida lorem. Ut turpis felis, pulvinar a semper sed, adipiscing id dolor. Pellentesque auctor nisi id magna consequat sagittis. Curabitur dapibus enim sit amet elit pharetra tincidunt feugiat nisl imperdiet. Ut convallis libero in urna ultrices accumsan. Donec sed odio eros. Donec viverra mi quis quam pulvinar at malesuada arcu rhoncus. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. In rutrum accumsan ultricies. Mauris vitae nisi at sem facilisis semper ac in est.</p>

  Commit your index.html back to your repository.  

## 5. Getting familiar with npm

  mkdir npmtest  
  cd npmtest  
  npm init  
  &gt; name: (npmtest): ENTER  
  &gt; version: (0.0.0) ENTER  
  &gt; description: first npm init ENTER  
  &gt; entry point: (index.js) ENTER  
  &gt; test command: ENTER  
  &gt; git repository: https://github.com/sunil-pandey/frontendproject ENTER  
  &gt; keywords: ENTER  
  &gt; license: (ISC) MIT ENTER  
  &gt; Is this ok? (yes) ENTER  

  Check created package.json file and it shall look like below:  

   <pre><code>
   {
      "name": "npmtest",
      "version": "0.0.0",
      "description": "first npm init",
      "main": "index.js",
      "scripts": {
         "test": "echo \"Error: no test specified\" && exit 1"
      },
      "repository": {
         "type": "git",
         "url": "https://github.com/sunil-pandey/frontendproject"
      },
      "author": "'Tushar",
      "license": "MIT",
      "bugs": {
         "url": "https://github.com/sunil-pandey/frontendproject/issues"
      },
      "homepage": "https://github.com/sunil-pandey/frontendproject"
   }
   </code></pre>

  - Create spec folder  
  mkdir spec  
  - Create test.js file in spec folder with the following content:  

  <pre><code>
  describe("A suite", function() {  
    it("contains spec with an expectation", function() {  
      expect(true).toBe(true);  
    });  
  });
  </code></pre>

  - Install gulp globally  
  npm install -g gulp  

  - Install gulp locally  
  npm install --save-dev gulp  

  - Install gulp-jasmine locally  
  npm install --save-dev gulp-jasmine  

  - Create gulpfile.js in npmdemo folder with the following contents  

  var gulp = require('gulp')  
  	jasmine = require('gulp-jasmine');  
	
  gulp.task('default', function () {  
      gulp.src('spec/test.js')  
          .pipe(jasmine());  
  });  

  - Run gulp command to get output similar to below:  

  [09:38:08] Using gulpfile D:\MyProjects\tushardemo\npmtest\gulpfile.js  
  [09:38:08] Starting 'default'...  
  [09:38:08] Finished 'default' after 28 ms  
  .

  Finished in 0.003 seconds  
  1 test, 1 assertion, 0 failures  

  - The final folder contents will be  

  <pre>
  npmtest
  |   gulpfile.js
  |   package.json
  |   
  +---node_modules
  |   +--- (lot of folders and files)
  |                                       
  \---spec
          test.js
  </pre>
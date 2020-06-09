# Creating Software Documentation in under 10 minutes with mkDocs
Why and how to quickly create professional documentation for your projects


As you work on any project, documentation is extremely helpful, almost critical. Luckily, mkDocs created a nice, efficient method of creating documentation that looks both professional and is easy-to-use.
## First, what is documentation and why does it matter?
Software documentation is writing about your code and your project, explaining what it is about and how it works. This is important for open-source projects, team projects, and even personal projects.
By documenting your code you:
<ol>
<li>Make your code explainable for others you're collaborating with (and for yourself when you later look back at your code!).</li>
<li>Keep track of all aspects of your software.</li>
<li>Helps make debugging easier later on.</li>
<li>Can have a universal space to keep your files.</li>
</ol>

It should only take at most 10 minutes to create the skeleton of your documentation with mkDocs. Spending 10 minutes to document now is worth having to spend countless minutes struggling to debug your code and explain  your code to your coworkers and yourself later.
##mkDocs Setup
To use mkDocs, you'll need pip. You can find instructions on how to install pip here. If you have pip, make sure to update it, then install mkDocs. While you install mkDocs, you should also pick a theme (check out the options here). In the example, we picked the material theme.
```
pip install --upgrade pip
pip install mkdocs
pip install mkdocs-material
```
Now you're ready to create your documentation. Run the below command, but replace PROJECT_NAME with whatever your project name is.
```
mkdocs new PROJECT_NAME
cd PROJECT_NAME
```
You should see a file called mkdocs.yaml and a folder called docs. The folder will have a single markdown file, index.md.
To run the documentation, use mkdocs serve and then go to http://127.0.0.1:8000/ in your browser. 
After running mkdocs serve, you'll see something like this at https://127.0.0.1:8000/.Open mkdocs.yaml and you should see the following:
```
site_name: My Docs
```
We're going to edit this document. First, we'll create a generic outline; feel free to fill in the placeholder variables. The theme is what we pip installed in the past.
```
site_name: NAME
nav:
  - Home: index.md
  - Page2: page2.md
  - Section1:
    - Subpage1: subpage1.md
    - Subpage2: subpage2.md
theme:
  name: THEME_DOWNLOADED
```
Let's take an example that I wanted to create documentation for an amusement park simulation. This is what I would do:
```
site_name: Amusement Park Simulation
nav:
  - Home: index.md
  - About: about.md
  - Games:
    - "Ping Pong": games/ping.md
    - Balloon: games/balloon.md
  - Rides:
    - "Scary Coaster": rides/scary.md
    - "Drop of Doom": rides/drop.md
theme:
  name: material
```
Note that all the folders and directories mentions in mkdocs.yaml will be in the docs directory. This is how my structure would look:
```
PROJECT_NAME/
    docs/
        index.md
        about.md
        games/
             ping.md
             balloon.md
        rides/
             scary.md
             drop.md
    mkdocs.yaml
    Add the rest of your code here
```
If you don't want several documents, categories can also be created with markdown header syntax. If you're unfamiliar with .md files, you can learn more about the syntax here.
The final version with just the outline. My next step is to fill my markdown files with content!
##Lastly, deploying.
To end, we'll host our documentation on GitHub Pages. Simply run mkdocs gh-deploy. It should create a new branch in your repository  that will host your site at USERNAME.github.io/REPOSITORY_NAME.
And that's it! You've successfully created documentation for your project. If you want to learn how to further customise your documentation or other mkDocs options, visit their website here. Check out my GitHub repository for this tutorial here and the deployed website here.
##Things to Note for Debugging
Make sure that you choose to use either tabs or spaces. mkDocs doesn't allow a combination of both.
If there are spaces in the name, add quotation marks.
If you're getting a 404 error, that means that you're probably missing a file. Check docs to make sure your file exists there.
If GitHub Pages isn't working, make sure that site isn't in your .gitignore.

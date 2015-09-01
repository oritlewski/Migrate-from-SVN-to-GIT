# Migrate-from-SVN-to-GIT
Process and commands to migrate from SVN to GIT

## Migration SVN -> GIT <strong>(une branche uniquement)</strong>

### Get authors list from SVN repo
java -jar ../svn-migration-scripts.jar authors <svn-repo> > authors.txt

### Get all biggest files to delete those unecessary
find . -size +100k

mkdir my_project_svn

cd my_project_svn

git svn init <repo url> --no-metadata

git config svn.authorsfile ../authors.txt 

git svn fetch

cd ..

git clone my_project_svn my_project

cd my_project

git remote set-url origin <git repo> {}

git push origin master

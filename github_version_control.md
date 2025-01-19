### How to make changes and syncronize the changes to Github using Microsoft VScode.

1. Clone repository from Github:                
  - Navigate to ```View```>```Source Control```>```Clone Repository```.                   
  - The system will ask you to ```Authorize Visual Studio Code``` to log in to Github.
2. Make changes to the project files.
  - Edit the project files as needed.
3. Stage and sync your changes:
  - Go to the ```Source Control``` again.
  - Click ```Stage Changes```, add your commit message, and then ```Sync Changes(This will push or pull changes)```.


### Update ```GEMS_TCO``` version

1. Go to the ```setup.py``` and make changes. For example ```version='0.1'``` to ```version='0.2'```.
2. Open ```New Terminal```
   ```git tag -a v0.2 -m "Release version 0.2"```            
   ```git push origin v0.2```

3. Check in the Github repository. One the right side, you see ```Rleases- tags```.             

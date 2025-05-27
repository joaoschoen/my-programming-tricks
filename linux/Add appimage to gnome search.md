# Problem

- When you download a .appimage program, gnome won't recognize it on it's search feature

# Solution

- Creating a .desktop file and updating the gnome desktop database

# Instructions

- Open your terminal
- Create the following folders
```sh 
mkdir ~/applications
mkdir ~/applications/icons
```
- Move your .appimage programs to the applications folder
- (Optional): Add icons to the /icons folder, either PNG or SVG
- (Optional): While where're here, you can create a link to the ./local/share/applications folder so navigation is easier in the future
```sh
ln -s /home/<your username>/.local/share/applications ./
```
- Navigate to:
```sh 
cd ~/.local/share/applications
```
- Create the .desktop file
```sh 
touch your_app_name.desktop #create the file
vim your_app_name.desktop #edit file
```
- Follow the example below to write the file:
```sh
[Desktop Entry]
Name=your_app_name #Name that will show up on the explorer
Comment=your_app_comment #Description that will show up on the explorer
Exec=/home/<your username>/applications/<your_app_name>.AppImage
Icon=/home/<your username>/applications/icons/<your_app_name>.png #Optional
Terminal=false #true if you want to run a CLI tool this way
Type=Application
Categories=Utility; #Game, Utility or Development, used by gnome for sorting
```
- After saving the file run the following command to update the .desktop database

```sh 
update-desktop-database ./
```
- Now the appimage will show up when you hit __Super/Windows__
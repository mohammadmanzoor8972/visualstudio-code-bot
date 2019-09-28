# visualstudio-code-bot
Visual Studio Code auto plugin added



ECHO OFF
REM Download Visual Studio Code and Installation
REM It take 5 Minute to download VS Code
REM Installation will start automaticly 
REM All mention Extention will be install
REM Folder Created
CALL powershell -Force new-item c:\mybot -itemtype directory
CALL powershell -Force new-item c:\mybot\extention -itemtype directory

	ECHO Extention Downloading....
	REM here is the syntax
	REM http://${publisher}.gallery.vsassets.io/_apis/public/gallery/publisher/${publisher}/extension/${extension name}/${version}/assetbyname/Microsoft.VisualStudio.Services.VSIXPackage
    CALL powershell -Command "(New-Object Net.WebClient).DownloadFile('http://dbaeumer.gallery.vsassets.io/_apis/public/gallery/publisher/dbaeumer/extension/vscode-eslint/0.10.18/assetbyname/Microsoft.VisualStudio.Services.VSIXPackage', 'extention\vscode-eslint.vsix')"
	CALL powershell -Command "(New-Object Net.WebClient).DownloadFile('http://wraith13.gallery.vsassets.io/_apis/public/gallery/publisher/wraith13/extension/wandbox-vscode/2.2.1/assetbyname/Microsoft.VisualStudio.Services.VSIXPackage', 'extention\wandbox-vscode.vsix')"
	CALL powershell -Command "(New-Object Net.WebClient).DownloadFile('http://alefragnani.gallery.vsassets.io/_apis/public/gallery/publisher/alefragnani/extension/delphi-pack/0.2.0/assetbyname/Microsoft.VisualStudio.Services.VSIXPackage', 'extention\delphi-pac.vsix')"
	ECHO Extention Downloaded....
  
REM mention all extention here
ECHO Extention Installing....
CALL code --install-extension extention\vscode-eslint.vsix
CALL code --install-extension extention\wandbox-vscode.vsix
CALL code --install-extension extention\delphi-pac.vsix

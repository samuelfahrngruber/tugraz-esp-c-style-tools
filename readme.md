# Manual formatting is annoying

That's why this repo has some tools to avoid any [style guide](https://tc.tugraz.at/main/mod/page/view.php?id=55770) violations in C for the ESP Assignments.

- `clang-format` (https://clang.llvm.org/docs/ClangFormat.html)
  can autoformat the code, e.g. putting braces on the correct line, having max. 120 characters per line

  _rules are defined in the `.clang-format` file._

- `clang-tidy` (https://clang.llvm.org/extra/clang-tidy/)
  can point out other issues in the code that cannot easily be auto-fixed e.g. having constants named in UPPERCASE etc.

  _rules are defined in the `.clang-tidy` file._

- `c-snippets`([style guide](https://tc.tugraz.at/main/mod/page/view.php?id=55770) conform)
contains file- and function-header comment snippets, for fast commenting your code
To use this, look in the `C_snippets.json` file for more information.

 >Normally these tools should work out of the box in VSCode/Codium if the [C++ extension](https://code.visualstudio.com/docs/languages/cpp) is installed.

This is not complete yet, and I did not test it a lot either - it should just make our life easier - if you find something in the [style guide](https://tc.tugraz.at/main/mod/page/view.php?id=55770) that I did not consider in the rule files, please add a PR and help your fellow students, thanks


# Setting up the tools
## 1.) Install the Requirements:

- ### C/C++ extension (https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools):

  #### There are two  options to install it:

    - search for it directly in the `VSCode Extension Manager`</br>
    
    - or `Download the VSIX` file and install it manually by opening the VSCode-commandline [Shift]+[Strg]+[P] and search for "VSIX". Select the "Install from VSIX...", and now you can navigate in the file explorer to the VSIX-file to install it.

- ### clang-format:
	  sudo apt-cache search clang-format
	  sudo apt-get install clang-format-<VERSION>
	  whereis clang-format-<VERSION>


## 2.) Cloning the tools

- direct to your `ESP-folder` via Terminal and then clone the repository:

      git clone https://github.com/samuelfahrngruber/tugraz-esp-c-style-tools.git

- after doing this drag all the files from `tugraz-esp-c-style-tools` into the `ESP-folder`.

## 3.) Editing the settings.json in VSCode

- To open up the global settings of VSCode: </br>`File ---> Settings ---> file-icon (at the top right)`

- Add this to the file:

      "clang-format.executable": "/usr/bin/clang-format-<VERSION>",
      "editor.tabSize": 2,
      "editor.formatOnSave": true,
      "editor.codeActionsOnSave": {
          "source.fixAll": true
      },
      "C_Cpp.codeAnalysis.runAutomatically": true,
      "C_Cpp.codeAnalysis.clangTidy.enabled": true,
      "clang-format.language.c.enable": true,
      "clang-format.style": "file",
      "clang-tidy.fixOnSave": true,
      "[c]": {
          "editor.defaultFormatter": "xaver.clang-format",
          "editor.wordBasedSuggestions": false,
          "editor.suggest.insertMode": "replace",
          "editor.semanticHighlighting.enabled": true,
      }


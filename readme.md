# Manual formatting is annoying

That's why this repo has some tools to avoid any [style guide](https://tc.tugraz.at/main/mod/page/view.php?id=55770) violations in C for the ESP Assignments.

- `clang-format` (https://clang.llvm.org/docs/ClangFormat.html)
  can autoformat the code, e.g. putting braces on the correct line, having max. 120 characters per line

  _rules are defined in the `.clang-format` file._

- `clang-tidy` (https://clang.llvm.org/extra/clang-tidy/)
  can point out other issues in the code that cannot easily be auto-fixed e.g. having constants named in UPPERCASE etc.

  _rules are defined in the `.clang-tidy` file._

Normally these tools should work out of the box in VSCode/Codium if the [C++ extension](https://code.visualstudio.com/docs/languages/cpp) is installed. Just copy the files into your assignment folder (including the `.vscode/settings.json`).

In the vscode settings file (`.vscode/settings.json`) is the config to automatically run `clang-tidy` code analysis (this will point out problems in your c file by underlining it red) and use `clang-format` automatically when saving the file, so it is never formatted wrongly. Also it adds the `clang` flags to show warnings etc.

This is not complete yet, and I did not test it a lot either - it should just make our life easier - if you find something in the [style guide](https://tc.tugraz.at/main/mod/page/view.php?id=55770) that I did not consider in the rule files, please add a PR and help your fellow students, thanks

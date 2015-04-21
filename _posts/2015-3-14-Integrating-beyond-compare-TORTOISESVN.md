---
layout: post
title: Integrating Beyond Compare  with TortoiseSVN as Diff Viewer and  3 way Merge Tool!
tags: [jekyll, documentation]
---


###Diff
Select Settings from Explorer's TortoiseSVN submenu.
Switch to the Diff Viewer tab.
Change the radio buttons from TortoiseMerge to External.
In the path edits, enter:
`C:\Program Files (x86)\Beyond Compare 4\BComp.exe" %base %mine /title1=%bname /title2=%yname /leftreadonly`
To use Beyond Compare for image comparisons either replace the file `C:\Program Files\TortoiseSVN\bin\TortoiseIDiff.exe with a copy of BComp.exe`, or click the Advanced button on the Diff Viewer tab and add each image type's extension with the same command line as above.

###3-way Merge 
Select Settings from Explorer's TortoisSVN submenu.
Switch to the Merge Tool tab.
Change the radio buttons from TortoiseMerge to External.
In the path edits, enter:
`C:\Program Files (x86)\Beyond Compare 4\BComp.exe" %mine %theirs %base %merged /title1=%yname /title2=%tname /title3=%bname /title4=%mname`

###2-way Merge
Use the same steps as above, but use the command line:
`C:\Program Files (x86)\Beyond Compare 4\BComp.exe" %mine %theirs /savetarget=%merged`
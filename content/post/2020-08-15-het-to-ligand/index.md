---
title: "Reclassifying Het Groups as Ligands in Schrödinger Maestro"
date: 2020-08-15
draft: false
description: "Preparing protein structures for ligand docking"
tags: [biology, ligand docking, troubleshooting]
categories:
- tutorial
---
*I did some ligand docking this summer using Schrödinger. I couldn't find instructions on how to reclassify a het group as a ligand in Maestro, so had to figure it out. What I did is documented here.*

When you import a structure of a protein bound to a ligand from [PDB](https://www.rcsb.org/), often the ligand isn't recognized as a ligand by [Maestro](https://www.schrodinger.com/maestro), Schrödinger's ligand docking software. This is problematic because then there's no ligand to select when generating a grid for ligand docking. Here are instructions on how to turn the het group into a ligand. I'm running Schrödinger 2020-2 on Windows 10. 

1. Find the het group in the structure hierarchy and extract it to a new entry
{{< figure src="select-het-group.jpeg" caption="" >}}
2. You should see a new entry in the entry list. Select it and go to **Edit -> 2D Sketcher**. Click on the "Save as New.." button at the bottom. 
{{< figure src="save-as-new.jpeg" caption="" >}}
As long the new stucture is under 130 atoms, it should be listed as a ligand now. 
{{< figure src="new-structure.jpeg" caption="" >}}
3. Select the new (ligand) stucture and the full protein structure in your workspace. Right click and merge them together. 
{{< figure src="select-both.jpeg" caption="" >}}
4. Select the merged structure. You should see your het group listed as a ligand now. 
{{< figure src="merged.jpeg" caption="" >}}

One of the potential downsides of this approach is that the exact conformation of the ligand is not preserved. This does not impact the grid generation, but if you want to compare the docked ligand to the original ligand, make sure that you're comparing it to the ligand that was not extracted and merged. If you want to preserve the exact conformation, I recommend editing the PDB file of the extracted ligand. 
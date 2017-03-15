---
title: "Utilisation d&#39;une biblioth&#232;que d&#39;importation et d&#39;un fichier d&#39;exportation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exportations circulaires"
  - "exporter des fichiers"
  - "bibliothèques d'importation, utilisation"
ms.assetid: 2634256a-8aa5-4495-8c9e-6cde10e4ed76
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Utilisation d&#39;une biblioth&#232;que d&#39;importation et d&#39;un fichier d&#39;exportation
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Quand un programme \(un fichier exécutable ou une DLL\) exporte vers un autre programme à partir duquel il importe aussi, ou si plusieurs programmes exportent et importent à la fois les uns des autres, les commandes pour lier ces programmes doivent pouvoir prendre en charge les exportations circulaires.  
  
 Dans une situation sans exportation circulaire, lors de la liaison d'un programme qui utilise des exportations à partir d'un autre programme, vous devez spécifier la bibliothèque d'importation pour le programme exportateur.  La bibliothèque d'importation du programme exportateur est créée lorsque vous liez ce programme exportateur.  Par conséquent, vous devez lier le programme exportateur avant le programme importateur.  Par exemple, si TWO.dll importe à partir du fichier ONE.dll, vous devez d'abord lier ONE.dll et obtenir la bibliothèque d'importation ONE.lib.  Vous devez spécifier ensuite ONE.lib lors de la liaison de TWO.dll.  Lorsque l'éditeur de liens crée TWO.dll, il crée également sa bibliothèque d'importation, TWO.lib.  Utilisez cette dernière lors de la liaison de programmes qui importent à partir de TWO.dll.  
  
 Cependant, dans une situation d'exportation circulaire, il n'est pas possible de lier tous les programmes interdépendants en utilisant des bibliothèques d'importation à partir des autres programmes.  Dans l'exemple décrit plus haut, si TWO.dll exporte également vers ONE.dll, la bibliothèque d'importation de TWO.dll n'existera pas encore quand ONE.dll sera lié.  Lorsque des exportations circulaires existent, vous devez utiliser LIB pour créer une bibliothèque d'importation et un fichier d'exportation pour l'un des programmes.  
  
 Pour commencer, choisissez l'un des programmes sur lequel exécuter LIB.  Dans la commande LIB, répertoriez tous les objets et bibliothèques associés au programme et spécifiez \/DEF.  Si le programme utilise un fichier .def ou des spécifications \/EXPORT, indiquez\-les également.  
  
 Après avoir créé la bibliothèque \(.lib\) d'importation et le fichier d'exportation \(.exp\) pour le programme, utilisez la bibliothèque d'importation lors de la liaison des autres programmes.  LINK crée une bibliothèque d'importation pour chaque programme exportateur qu'il génère.  Par exemple, si vous exécutez LIB sur les objets et exportations du fichier ONE.dll, vous créez les fichiers ONE.lib et ONE.exp.  Vous pouvez désormais utiliser ONE.lib lors de la liaison de TWO.dll ; cette étape crée également la bibliothèque d'importation TWO.lib.  
  
 Enfin, liez le programme par lequel vous avez commencé.  Dans la commande LINK, spécifiez les objets et les bibliothèques du programme, le fichier .exp que LIB a créé pour le programme et les bibliothèques d'importation pour les exportations utilisées par le programme.  Pour poursuivre l'exemple, la commande LINK relative à ONE.dll contient ONE.exp et TWO.lib, ainsi que les objets et bibliothèques importés dans ONE.dll.  Ne spécifiez pas le fichier .def ou les spécifications \/EXPORT dans la commande LINK ; ils ne sont pas requis car les définitions d'exportation sont contenues dans le fichier .exp.  Quand vous liez un fichier .exp, LINK ne crée pas une bibliothèque d'importation puisqu'il suppose qu'une telle bibliothèque a été créée en même temps que le fichier .exp.  
  
## Voir aussi  
 [Utilisation de bibliothèques d'importation et de fichiers d'exportation](../../build/reference/working-with-import-libraries-and-export-files.md)
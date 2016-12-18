---
title: "Calcul des valeurs n&#233;cessaires | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonctions d'assistance, calculer les valeurs nécessaires"
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Calcul des valeurs n&#233;cessaires
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Deux informations très importantes doivent être calculées par la routine d'assistance de chargement différé.  Il existe à cet effet deux fonctions inline dans le fichier delayhlp.cpp permettant de calculer ces informations.  
  
-   La première calcule l'index de l'importation active dans les trois tables IAT \(import address table\), BIAT \(bound import address table\) et UIAT \(unbound import address table\).  
  
-   La seconde comptabilise le nombre d'importations dans une table IAT valide.  
  
```  
// utility function for calculating the index of the current import  
// for all the tables (INT, BIAT, UIAT, and IAT).  
__inline unsigned  
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {  
    return pitdCur - pitdBase;  
    }  
  
// utility function for calculating the count of imports given the base  
// of the IAT. NB: this only works on a valid IAT!  
__inline unsigned  
CountOfImports(PCImgThunkData pitdBase) {  
    unsigned        cRet = 0;  
    PCImgThunkData  pitd = pitdBase;  
    while (pitd->u1.Function) {  
        pitd++;  
        cRet++;  
        }  
    return cRet;  
    }  
```  
  
## Voir aussi  
 [Understanding the Helper Function](http://msdn.microsoft.com/fr-fr/6279c12c-d908-4967-b0b3-cabfc3e91d3d)
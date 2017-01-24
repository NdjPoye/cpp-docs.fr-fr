---
title: "D&#233;finition de fonctions inline C++ avec dllexport et dllimport | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dllexport (attribut) (C++), fonctions inline"
  - "dllimport (attribut) (C++), fonctions inline"
  - "fonctions (C++), définir inline"
  - "fonctions inline (C++), définition"
ms.assetid: 3b48678b-e7b8-4eda-bb46-b5d34dcf7817
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;finition de fonctions inline C++ avec dllexport et dllimport
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Vous pouvez définir comme inline une fonction avec l'attribut `dllexport`.  Dans ce cas, la fonction est toujours instanciée et exportée, qu'elle soit référencée ou non par un module du programme.  La fonction est présumée être importée par un autre programme.  
  
 Vous pouvez également définir comme inline une fonction déclarée avec l'attribut **dllimport**.  Dans ce cas, la fonction peut être développée \(soumise aux spécifications \/Ob\) mais jamais instanciée.  En particulier, si l'adresse d'une fonction importée inline est reçue, l'adresse de la fonction résidant dans la DLL est retournée.  Ce comportement est identique à la réception de l'adresse d'une fonction importée non inline.  
  
 Ces règles s'appliquent aux fonctions inline dont les définitions apparaissent dans une définition de classe.  De plus, les données locales statiques et les chaînes des fonctions inline conservent les mêmes identités entre la DLL et le client qu'elles le feraient dans un programme unique \(autrement dit un fichier exécutable sans interface DLL\).  
  
 Soyez vigilant en fournissant des fonctions inline importées.  Par exemple, si vous mettez à jour la DLL, ne supposez pas que le client utilisera sa version modifiée.  Pour vous assurer que vous chargez la version appropriée de la DLL, régénérez aussi le client de la DLL.  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)
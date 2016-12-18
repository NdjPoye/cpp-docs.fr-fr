---
title: "Construction d&#39;objets de flux de sortie | Microsoft Docs"
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
  - "objets de flux de sortie"
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Construction d&#39;objets de flux de sortie
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous utilisez uniquement `cout`prédéfini, `cerr`, ou les objets d'`clog`, vous n'avez pas besoin de créer un flux de sortie.  Vous devez utiliser les constructeurs pour :  
  
-   [Constructeurs de sortie de flux de fichier](#vclrfoutputfilestreamconstructorsanchor1)  
  
-   [Constructeurs de sortie de flux de données de chaîne](#vclrfoutputstringstreamconstructorsanchor2)  
  
##  <a name="vclrfoutputfilestreamconstructorsanchor1"></a> Constructeurs de sortie de flux de fichier  
 Vous pouvez construire un flux de sortie de deux manières :  
  
-   Utilisez le constructeur par défaut, puis appelez la fonction membre d'`open`.  
  
    ```  
    ofstream myFile; // Static or on the stack  
    myFile.open( "filename" );  
  
    ofstream* pmyFile = new ofstream; // On the heap  
    pmyFile->open( "filename" );  
    ```  
  
-   Spécifiez les indicateurs d'un nom de fichier et de mode dans l'appel du constructeur.  
  
    ```  
    ofstream myFile( "filename", ios_base::out);  
    ```  
  
##  <a name="vclrfoutputstringstreamconstructorsanchor2"></a> Constructeurs de sortie de flux de données de chaîne  
 Pour construire un flux de sortie de chaîne, vous pouvez utiliser `ostringstream` de la manière suivante :  
  
```  
   using namespace std;  
string sp;  
ostringstream myString;  
myString << "this is a test" << ends;  
sp = myString.str();  // Obtain string  
cout << sp < endl;   
```  
  
 `ends` « manipulateur » ajoute le caractère NULL de fin nécessaire avec la chaîne.  
  
## Voir aussi  
 [Flux de sortie](../standard-library/output-streams.md)
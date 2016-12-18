---
title: "Construction d&#39;objets de flux d&#39;entr&#233;e | Microsoft Docs"
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
  - "objets de flux d'entrée"
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Construction d&#39;objets de flux d&#39;entr&#233;e
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous utilisez uniquement l'objet d'`cin`, vous n'avez pas besoin de construire un flux d'entrée.  Vous devez créer un flux d'entrée si vous utilisez :  
  
-   [Constructeurs de flux de fichier d'entrée](#vclrfinputfilestreamconstructorsanchor8)  
  
-   [Constructeurs d'entrée de flux de données de chaîne](#vclrfinputstringstreamconstructorsanchor9)  
  
##  <a name="vclrfinputfilestreamconstructorsanchor8"></a> Constructeurs de flux de fichier d'entrée  
 Il existe deux méthodes pour créer un flux de fichier d'entrée :  
  
-   Utilisez le constructeur d'argument de `void`, puis appelez la fonction membre d'`open` :  
  
    ```  
    ifstream myFile; // On the stack  
    myFile.open( "filename" );  
  
    ifstream* pmyFile = new ifstream; // On the heap  
    pmyFile->open( "filename" );  
    ```  
  
-   Spécifiez les indicateurs d'un nom de fichier et de mode dans l'appel du constructeur, ouvrez ainsi le fichier pendant le processus de construction :  
  
    ```  
    ifstream myFile( "filename" );  
    ```  
  
##  <a name="vclrfinputstringstreamconstructorsanchor9"></a> Constructeurs d'entrée de flux de données de chaîne  
 Les constructeurs d'entrée de flux de données de chaîne requièrent l'adresse du stockage préaffecté et préinitialisé :  
  
```  
string s("123.45");  
double amt;  
istringstream myString( s );   
//istringstream myString( "123.45" ) also works  
myString >> amt; // amt contains 123.45  
```  
  
## Voir aussi  
 [Flux d'entrée](../standard-library/input-streams.md)
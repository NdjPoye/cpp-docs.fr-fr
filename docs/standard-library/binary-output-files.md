---
title: "Fichiers de sortie binaires | Microsoft Docs"
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
  - "données binaires, fichiers de sortie binaires"
  - "fichiers (C++), fichiers de sortie binaires"
  - "E/S (C++), fichiers de sortie binaires"
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fichiers de sortie binaires
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les flux de données ont été initialement conçus pour le texte, afin que le mode de sortie par défaut soit du texte.  En mode texte, le caractère de saut de ligne \(hexadécimal 10\) s'étend à un retour chariot CRLF \(16 bits uniquement\).  L'expansion peut entraîner des problèmes, comme montré ici :  
  
```  
// binary_output_files.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
int main( )  
{  
    ofstream os( "test.dat" );  
    os.write( (char *) iarray, sizeof( iarray ) );  
}  
```  
  
 Vous pouvez vous attendre à ce que programme renvoie la séquence byte {99, 0, 10, 0} ; mais il renvoie {99, 0, 13, 10, 0} à la place, ce qui pose problèmes pour un programme à entrées binaires.  Si vous avez besoin de vrais résultat binaire, dans laquelle les caractères sont écrits non traduits, vous pouvez spécifier le résultat binaire avec l'argument du mode de construction [ofstream](../Topic/ofstream.md):  
  
```  
// binary_output_files2.cpp  
// compile with: /EHsc  
#include <fstream>  
using namespace std;  
int iarray[2] = { 99, 10 };  
  
int main()  
{  
   ofstream ofs ( "test.dat", ios_base::binary );  
  
   // Exactly 8 bytes written  
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );   
}  
```  
  
## Voir aussi  
 [Flux de sortie](../standard-library/output-streams.md)
---
title: "Manipulateurs de flux de sortie &#224; un argument (int ou long) | Microsoft Docs"
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
  - "flux de sortie, int ou long (argument) (manipulateurs)"
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Manipulateurs de flux de sortie &#224; un argument (int ou long)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque iostream de la classe fournit un ensemble de macros pour créer des manipulateurs paramétrables.  Les manipulateurs avec un argument unique `int` ou `long` sont un cas spécial.  Pour créer un manipulateur de flux de sortie qui reçoit un argument unique `int` ou `long` \(comme `setw`\), vous devez utiliser la macro de \_Smanip, qui est définie dans l' \<iomanip\>.  Cet exemple définit un manipulateur `fillblank` qui insère un nombre spécifié d'espaces dans le flux de données :  
  
## Exemple  
  
```  
// output_stream_manip.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <iomanip>  
using namespace std;  
  
void fb( ios_base& os, int l )  
{  
   ostream *pos = dynamic_cast<ostream*>(&os);  
   if (pos)  
   {  
      for( int i=0; i < l; i++ )  
      (*pos) << ' ';  
   };  
}  
  
_Smanip<int>  
   __cdecl fillblank(int no)  
   {     
   return (_Smanip<int>(&fb, no));  
   }  
  
int main( )  
{  
   cout << "10 blanks follow" << fillblank( 10 ) << ".\n";  
}  
```  
  
## Voir aussi  
 [Manipulateurs personnalisés avec arguments](../standard-library/custom-manipulators-with-arguments.md)
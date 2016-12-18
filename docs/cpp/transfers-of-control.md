---
title: "Transferts de contr&#244;le | Microsoft Docs"
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
  - "flux de contrôle, créer une branche"
  - "flux de contrôle, transférer le contrôle"
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Transferts de contr&#244;le
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser l'instruction `goto` ou une étiquette **case** dans une instruction `switch` pour spécifier un programme qui crée une branche après un initialiseur.  Ce code est conforme sauf si la déclaration qui contient l'initialiseur figure dans un bloc se trouvant lui\-même dans le bloc dans lequel l'instruction de saut s'exécute.  
  
 L'exemple suivant montre une boucle qui déclare et initialise les objets `total`, `ch` et `i`.  Il comporte également une instruction `goto` erronée qui transfère le contrôle après un initialiseur.  
  
```  
// transfers_of_control.cpp  
// compile with: /W1  
// Read input until a nonnumeric character is entered.  
int main()  
{  
   char MyArray[5] = {'2','2','a','c'};  
   int i = 0;  
   while( 1 )  
   {  
      int total = 0;  
  
      char ch = MyArray[i++];  
  
      if ( ch >= '0' && ch <= '9' )  
      {  
         goto Label1;  
  
         int i = ch - '0';  
      Label1:  
         total += i;   // C4700: transfers past initialization of i.  
      } // i would be destroyed here if  goto error were not present  
   else  
      // Break statement transfers control out of loop,  
      //  destroying total and ch.  
      break;  
   }  
}  
```  
  
 Dans l'exemple précédent, l'instruction `goto` tente de transférer le contrôle après l'initialisation de `i`.  Toutefois, si `i` était déclaré mais non initialisé, le transfert serait conforme.  
  
 Les objets `total` et `ch`, déclarés dans le bloc qui sert de *statement* à l'instruction `while`, sont détruits lors de la sortie de ce bloc avec l'instruction `break`.  
  
## Voir aussi  
 [\(NOTINBUILD\) Declaration of Automatic Objects](http://msdn.microsoft.com/fr-fr/81f941e9-c1b1-4d1c-a28d-70b6ee9765db)
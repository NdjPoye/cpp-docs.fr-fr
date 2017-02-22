---
title: "Avertissement du compilateur (niveau 4) C4256 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4256"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4256"
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau 4) C4256
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : le constructeur pour la classe avec bases virtuelles a '...' ; les appels peuvent ne pas être compatibles avec les anciennes versions de Visual C\+\+  
  
 Incompatibilité possible.  
  
 Prenons l'exemple de code suivant.  Si la définition du constructeur S2::S2 \(int i,… \) a été compilée avec une version du compilateur Visual C\+\+ antérieure à la version 7, mais l'exemple suivant est compilé à l'aide de la version actuelle, l'appel au constructeur de S3 ne travaillerait pas correctement en raison d'une modification de convention d'appel de cas.  Si les deux étaient compilés avec Visual C\+\+ 6.0, l'appel ne fonctionnerait pas correctement non plus, sauf si aucun paramètre n'était passé à la place des points de suspension.  
  
 Pour remédier à cet avertissement :  
  
1.  N'utilisez pas de points de suspension dans un constructeur.  
  
2.  Vérifiez que tous les composants dans leur projet sont générés avec la version actuelle \(y compris les bibliothèques pouvant définir ou référencer cette classe\), puis désactivez l'avertissement à l'aide du pragma [warning](../../preprocessor/warning.md).  
  
 L'exemple suivant génère l'erreur C4256 :  
  
```  
// C4256.cpp  
// compile with: /W4  
// #pragma warning(disable : 4256)  
struct S1  
{  
};  
  
struct S2: virtual public S1  
{  
   S2( int i, ... )    // C4256  
   {  
      i = 0;  
   }  
   /*  
   // try the following line instead  
   S2( int i)  
   {  
      i = 0;  
   }  
   */  
};  
  
void func1()  
{  
   S2 S3( 2, 1, 2 );   // C4256  
   // try the following line instead  
   // S2 S3( 2 );  
}  
  
int main()  
{  
}  
```
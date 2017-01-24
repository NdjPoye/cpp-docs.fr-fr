---
title: "Instruction return dans la terminaison du programme (C++) | Microsoft Docs"
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
  - "types de données (C++), types de retours de fonction"
  - "types de retours de fonction, return (instruction)"
  - "return (mot clé) (C++), syntaxe"
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Instruction return dans la terminaison du programme (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Du point de vue fonctionnel, émettre une instruction `return` à partir de **main** équivaut à appeler la fonction **exit**.  Prenons l'exemple suivant :  
  
```  
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 Les instructions **exit** et `return` de l'exemple précédent sont identiques du point de vue fonctionnel.  Toutefois, C\+\+ exige que les fonctions dont les types de retour sont différents de `void` retournent une valeur.  L'instruction `return` vous permet de retourner une valeur à partir de **main**.  
  
## Voir aussi  
 [Terminaison du programme](../cpp/program-termination.md)
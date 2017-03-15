---
title: "Avertissement de ligne de commande D9041 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9041"
ms.assetid: ada8815f-4246-4e25-b57d-a7f16fa107cc
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Avertissement de ligne de commande D9041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

valeur 'value' non valide pour '\/option' ; 'value' par défaut ; ajoutez '\/analyze' aux options de ligne de commande lors de la spécification de cet avertissement  
  
 Un numéro d'avertissement lié à l'analyse du code a été ajouté à l'option de ligne de commande **\/wd**, **\/we**, **\/wo** ou **\/wl** sans spécifier également l'option de ligne de commande **\/analyze**.  Pour remédier à cette erreur, ajoutez l'option de ligne de commande **\/analyze** ou supprimez le numéro d'avertissement non valide de l'option de ligne de commande **\/w** appropriée.  
  
## Exemple  
 L'exemple de ligne de commande suivant génère l'avertissement D9041 :  
  
```  
cl /EHsc /LD /wd6001 filename.cpp  
```  
  
 Pour résoudre l'avertissement, ajoutez l'option de ligne de commande **\/analyze**.  Si l'option **\/analyze** n'est pas prise en charge sur votre version du compilateur, supprimez le numéro d'avertissement non valide de l'option **\/wd**.  
  
## Voir aussi  
 [Erreurs de ligne de commande D8000 à D9999](../../error-messages/tool-errors/command-line-errors-d8000-through-d9999.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)
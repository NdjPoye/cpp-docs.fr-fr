---
title: "Op&#233;rateurs binaires | Microsoft Docs"
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
  - "opérateurs binaires"
  - "opérateurs de sélection de membres"
  - "opérateurs (C++), binaire"
ms.assetid: c0e7fbff-bc87-4708-8333-504ac09ee83e
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs binaires
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant affiche une liste des opérateurs qui peuvent être surchargés.  
  
### Opérateurs binaires redéfinissables  
  
|Opérateur|Nom|  
|---------------|---------|  
|**,**|Virgule|  
|`!=`|Inégalité|  
|`%`|Modulo|  
|`%=`|Modulo\/assignation|  
|**&**|Opération de bits AND|  
|**&&**|AND logique|  
|**&\=**|Opération de bits AND\/assignation|  
|**\***|Multiplication|  
|**\*\=**|Multiplication\/assignation|  
|**\+**|Addition|  
|`+=`|Addition\/assignation|  
|**–**|Soustraction|  
|**–\=**|Soustraction\/assignation|  
|**–\>**|Sélection de membres|  
|**–\>\***|Sélection de pointeur de membre|  
|**\/**|Division|  
|`/=`|Division\/assignation|  
|**\<**|Inférieur à|  
|**\<\<**|Décalage vers la gauche|  
|**\<\<\=**|Décalage vers la gauche\/assignation|  
|**\<\=**|Inférieur ou égal à|  
|**\=**|Assignation|  
|`==`|Égalité|  
|**\>**|Supérieur à|  
|**\>\=**|Supérieur ou égal à|  
|**\>\>**|Décalage vers la droite|  
|**\>\>\=**|Décalage vers la droite\/assignation|  
|**^**|OR exclusive|  
|`^=`|OR exclusive\/assignation|  
|**&#124;**|Opération de bits OR inclusive|  
|`&#124;=`|OR inclusive au niveau du bit\/assignation|  
|`&#124;&#124;`|Opérateur OR logique|  
  
 Pour déclarer une fonction d'opérateur binaire en tant que membre non statique, vous devez la déclarer comme suit :  
  
 *ret\-type* **operator**`op`**\(** `arg` **\)**  
  
 où *ret\-type* est le type de retour, `op` est l'un des opérateurs répertoriés dans le tableau précédent, et `arg` est un argument de tout type.  
  
 Pour déclarer une fonction d'opérateur binaire en tant que fonction globale, vous devez la déclarer comme suit :  
  
 *ret\-type* **operator**`op`**\(** `arg1`**,** `arg2` **\)**  
  
 où *ret\-type* et `op` apparaissent tels qu'ils sont décrits pour les fonctions d'opérateur de membre, et `arg1` et `arg2` sont les arguments.  Au moins un des arguments doit être de type classe.  
  
> [!NOTE]
>  Il n'existe aucune restriction sur les types de retour des opérateurs binaires. En revanche, la plupart des opérateurs binaires définis par l'utilisateur retournent un type de classe ou une référence à un type de classe.  
  
## Voir aussi  
 [Surcharge d'opérateur](../cpp/operator-overloading.md)
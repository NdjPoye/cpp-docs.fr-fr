---
title: "Opérateurs binaires | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- member-selection operators [C++]
- operators [C++], binary
- binary operators [C++]
ms.assetid: c0e7fbff-bc87-4708-8333-504ac09ee83e
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 384ac135c7ecb63b864160723984ef5d271e1395
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="binary-operators"></a>Opérateurs binaires
Le tableau suivant affiche une liste des opérateurs qui peuvent être surchargés.  
  
### <a name="redefinable-binary-operators"></a>Opérateurs binaires redéfinissables  
  
|Opérateur|Name|  
|--------------|----------|  
|**,**|Virgule|  
|`!=`|Inégalité|  
|`%`|Modulo|  
|`%=`|Modulo/assignation|  
|**&**|Opération de bits AND|  
|**&&**|AND logique|  
|**&=**|Opération de bits AND/assignation|  
|**\***|Multiplication|  
|**\*=**|Multiplication/assignation|  
|**+**|Addition|  
|`+=`|Addition/assignation|  
|**-**|Soustraction|  
|**-=**|Soustraction/assignation|  
|**->**|Sélection de membres|  
|**->\***|Sélection de pointeur de membre|  
|**/**|Division|  
|`/=`|Division/assignation|  
|**<**|Inférieur à|  
|**<<**|Décalage vers la gauche|  
|**<<=**|Décalage vers la gauche/assignation|  
|**<=**|Inférieur ou égal à|  
|**=**|Attribution|  
|`==`|Égalité|  
|**>**|Supérieur à|  
|**>=**|Supérieur ou égal à|  
|**>>**|Décalage vers la droite|  
|**>>=**|Décalage vers la droite/assignation|  
|**^**|OR exclusive|  
|`^=`|OR exclusive/assignation|  
|**&#124;**|Opération de bits OR inclusive|  
|`&#124;=`|OR inclusive au niveau du bit/assignation|  
|`&#124;&#124;`|OR logique|  
  
 Pour déclarer une fonction d'opérateur binaire en tant que membre non statique, vous devez la déclarer comme suit :  
  
 *RET-type* **opérateur**`op`**(** `arg` **)**  
  
 où *ret-type* est le type de retour, `op` est un des opérateurs répertoriés dans le tableau précédent, et `arg` est un argument de n’importe quel type.  
  
 Pour déclarer une fonction d'opérateur binaire en tant que fonction globale, vous devez la déclarer comme suit :  
  
 *RET-type* **opérateur**`op`**(** `arg1` **,** `arg2` **)**  
  
 où *ret-type* et `op` sont celles décrites pour les fonctions d’opérateur de membre et `arg1` et `arg2` sont des arguments. Au moins un des arguments doit être de type classe.  
  
> [!NOTE]
>  Il n’existe aucune restriction sur les types de retour des opérateurs binaires. En revanche, la plupart des opérateurs binaires définis par l’utilisateur retournent un type de classe ou une référence à un type de classe.  
  
## <a name="see-also"></a>Voir aussi  
 [Surcharge d'opérateur](../cpp/operator-overloading.md)

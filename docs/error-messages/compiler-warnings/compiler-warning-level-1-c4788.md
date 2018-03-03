---
title: Compilateur avertissement (niveau 1) C4788 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4788
dev_langs:
- C++
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e6f876dada851f46b7708ef1b34da4bae6f96dc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4788"></a>Avertissement du compilateur (niveau 1) C4788
'identificateur' : identificateur tronqué à 'nombre' caractères  
  
 Le compilateur limite la longueur maximale autorisée pour un nom de fonction. Lorsque le compilateur génère des funclets pour le code EH/SEH, il constitue le nom funclet en ajoutant le nom de fonction avec du texte, par exemple « __catch, » «\__unwind », ou une autre chaîne.  
  
 Le nom de funclet résultant peut être trop long, et le compilateur sera tronqué et générer C4788.  
  
 Pour résoudre cet avertissement, raccourcissez le nom de fonction d’origine. Si la fonction est une fonction de modèle C++ ou une méthode, utilisez un typedef pour une partie du nom. Exemple :  
  
```  
C1<x, y, z<T>>::C2<a,b,c>::f  
```  
  
 peut être remplacé par :  
  
```  
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;  
new_class::f  
```  
  
 Cet avertissement se produit uniquement dans le [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] compilateur.
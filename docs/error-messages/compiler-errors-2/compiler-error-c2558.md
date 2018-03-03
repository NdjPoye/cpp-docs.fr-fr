---
title: Erreur du compilateur C2558 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2558
dev_langs:
- C++
helpviewer_keywords:
- C2558
ms.assetid: 822b701e-dcae-423a-b21f-47f36aff9c90
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3224a612a41a87c76cd774f50e49d523bd24d06c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2558"></a>Erreur du compilateur C2558
'identificateur' : pas de constructeur de copie disponible ou le constructeur de copie est déclaré 'explicit'  
  
 Un constructeur de copie initialise un objet d'un autre objet de même type. (Il fait une copie de l'objet.) Le compilateur génère un constructeur de copie par défaut si vous ne définissez pas de constructeur.  
  
### <a name="to-fix-this-error"></a>Pour corriger cette erreur  
  
1.  Le problème peut se produire lors d'une tentative de copie d'une classe dont le constructeur de copie est `private`. Le plus souvent, une classe qui a un constructeur de copie `private` ne doit pas être copiée. Une technique de programmation classique déclare un constructeur de copie `private` pour éviter l'utilisation directe d'une classe. La classe peut être inutile en tant que telle ou nécessiter une autre classe afin de fonctionner correctement.  
  
     Si vous pensez que l'utilisation d'une classe qui a un constructeur de copie `private` ne présente aucun risque, dérivez une nouvelle classe à partir de la classe ayant le constructeur `private` et mettez un constructeur de copie `public` ou `protected` à la disposition de la nouvelle classe. Utilisez la classe dérivée à la place de l'original.  
  
2.  Le problème peut se produire lors d'une tentative de copie d'une classe dont le constructeur de copie est explicite. La déclaration d'un constructeur de copie comme `explicit` évite le passage ou le retour d'objets d'une classe depuis ou vers les fonctions. Pour plus d’informations sur les constructeurs explicites, consultez [des Conversions de types définis par l’utilisateur](../../cpp/user-defined-type-conversions-cpp.md).  
  
3.  Le problème peut se produire lors d'une tentative de copie d'une instance de classe déclarée `const` à l'aide d'un constructeur de copie qui n'accepte pas de paramètre de référence `const`. Déclarez votre constructeur de copie avec une référence de type `const` au lieu d'une référence de type non const.
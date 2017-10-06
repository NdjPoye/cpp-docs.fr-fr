---
title: "À l’aide de la gestion structurée des exceptions avec C++ | Documents Microsoft"
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
- C++ exception handling, mixed with SEH
- structured exception handling [C++], with C++ exception handling
ms.assetid: ec34b528-8c26-4429-b24a-6a68553aaa91
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 8f9805479d7ee9589cfd0da8491b0344d0bd7de1
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="using-structured-exception-handling-with-c"></a>Utilisation de la gestion structurée des exceptions avec C++
La gestion structurée des exceptions décrite dans ces articles fonctionne avec les fichiers sources C et C++. Toutefois, elle n'est pas conçue spécifiquement pour C++ et n'est pas recommandée. Vous pouvez vous assurer que votre code est plus portable en utilisant la gestion des exceptions C++. En outre, le mécanisme de gestion des exceptions C++ est plus souple, car il peut gérer les exceptions de tout type.  
  
 Microsoft C++ prend désormais en charge le modèle de gestion des exceptions C++, basé sur la norme C++ ANSI. Ce mécanisme gère automatiquement la destruction des objets locaux pendant le déroulement de la pile. Si vous écrivez du code C++ à tolérance de panne et que vous souhaitez implémenter la gestion des exceptions, nous vous recommandons vivement d'utiliser la gestion des exceptions C++ plutôt que la gestion structurée des exceptions. (Notez que bien que le compilateur C++ prenne en charge les constructions de gestion structurée des exceptions comme décrit dans des articles, le compilateur C standard ne prend pas en charge la syntaxe de gestion des exceptions C++.) Pour plus d’informations sur la gestion des exceptions C++, consultez [gestion des exceptions C++](../cpp/cpp-exception-handling.md) et *manuel de référence C++ annoté* par Margaret Ellis et Bjarne Stroustrup.  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion structurée des exceptions (C/C++)](../cpp/structured-exception-handling-c-cpp.md)

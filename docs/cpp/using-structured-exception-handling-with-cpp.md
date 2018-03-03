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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: db5d067a391512d56a2d01ce3052ac3fab061f28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-structured-exception-handling-with-c"></a>Utilisation de la gestion structurée des exceptions avec C++
La gestion structurée des exceptions décrite dans ces articles fonctionne avec les fichiers sources C et C++. Toutefois, elle n'est pas conçue spécifiquement pour C++ et n'est pas recommandée. Vous pouvez vous assurer que votre code est plus portable en utilisant la gestion des exceptions C++. En outre, le mécanisme de gestion des exceptions C++ est plus souple, car il peut gérer les exceptions de tout type.  
  
 Microsoft C++ prend désormais en charge le modèle de gestion des exceptions C++, basé sur la norme C++ ANSI. Ce mécanisme gère automatiquement la destruction des objets locaux pendant le déroulement de la pile. Si vous écrivez du code C++ à tolérance de panne et que vous souhaitez implémenter la gestion des exceptions, nous vous recommandons vivement d'utiliser la gestion des exceptions C++ plutôt que la gestion structurée des exceptions. (Notez que bien que le compilateur C++ prenne en charge les constructions de gestion structurée des exceptions comme décrit dans des articles, le compilateur C standard ne prend pas en charge la syntaxe de gestion des exceptions C++.) Pour plus d’informations sur la gestion des exceptions C++, consultez [gestion des exceptions C++](../cpp/cpp-exception-handling.md) et *manuel de référence C++ annoté* par Margaret Ellis et Bjarne Stroustrup.  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion structurée des exceptions (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
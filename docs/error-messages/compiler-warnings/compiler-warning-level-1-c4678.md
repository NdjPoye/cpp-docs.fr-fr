---
title: Compilateur avertissement (niveau 1) C4678 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4678
dev_langs:
- C++
helpviewer_keywords:
- C4678
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: d35e60d60d194bc0ca68a116dc45b6d9864d9fe2
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4678"></a>Avertissement du compilateur (niveau 1) C4678
la classe de base 'base_type' est moins accessible que 'derived_type'  
  
Un type public dérive d’un type privé. Si le type public est instancié dans un assembly référencé, les membres du type de base privé ne sont pas accessibles.  
  
C4678 est uniquement accessible à l’aide de l’option du compilateur obsolètes **/CLR : oldSyntax**. C’est une erreur lors de l’utilisation **/clr**, pour avoir une classe de base qui est moins accessible que sa classe dérivée.  


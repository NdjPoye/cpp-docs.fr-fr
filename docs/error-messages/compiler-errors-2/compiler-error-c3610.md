---
title: Erreur du compilateur C3610 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3610
dev_langs:
- C++
helpviewer_keywords:
- C3610
ms.assetid: 9349a348-9d37-4a00-9eab-481039268d31
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 31cef33981bbc2063bf68e433f9d3ba32780363d
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3610"></a>Erreur du compilateur C3610
'valuetype' : type de valeur doit être 'boxed' avant de pouvoir appeler la méthode 'méthode'  
  
 Par défaut, un type valeur n’est pas sur le tas managé. Avant que vous pouvez appeler des méthodes depuis les classes de runtime .NET, tel que `Object`, vous devez déplacer le type valeur vers le tas managé.  
  
 C3610 est uniquement accessible à l’aide de l’option du compilateur obsolètes **/CLR : oldSyntax**.  


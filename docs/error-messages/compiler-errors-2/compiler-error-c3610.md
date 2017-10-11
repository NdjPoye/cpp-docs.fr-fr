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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0cacac87535864c6268d0f078566b9ab224e9151
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3610"></a>Erreur du compilateur C3610
'valuetype' : type de valeur doit être 'boxed' avant l’appel de méthode 'méthode'  
  
 Par défaut, un type valeur n’est pas sur le tas managé. Avant que vous pouvez appeler les méthodes de classes de runtime .NET, tel que `Object`, vous devez déplacer le type de valeur dans le tas managé.  
  
 C3610 est uniquement accessible à l’aide de l’option du compilateur obsolète **oldSyntax ;**.  


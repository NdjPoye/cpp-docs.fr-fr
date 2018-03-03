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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 33fba9e64a6d314d503a42d0cf5512a2edb9c3a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3610"></a>Erreur du compilateur C3610
'valuetype' : type de valeur doit être 'boxed' avant l’appel de méthode 'méthode'  
  
 Par défaut, un type valeur n’est pas sur le tas managé. Avant que vous pouvez appeler les méthodes de classes de runtime .NET, tel que `Object`, vous devez déplacer le type de valeur dans le tas managé.  
  
 C3610 est uniquement accessible à l’aide de l’option du compilateur obsolète **oldSyntax ;**.  

---
title: Erreur du compilateur C2592 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2592
dev_langs: C++
helpviewer_keywords: C2592
ms.assetid: 833a4d7b-66ef-4d4c-ae83-a533c2b0eb07
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5f6483a168ffe5f7b487932770226c834b7fd611
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2592"></a>Erreur du compilateur C2592
'classe' : 'base_class_2' est hérité de 'base_class_1' et ne peut pas être spécifié de nouveau  
  
 Vous ne pouvez spécifier que les classes de base qui n'héritent pas d'autres classes de base. Dans ce cas, seul `base_class_1` est nécessaire dans la spécification de `class` car `base_class_1` hérite déjà de `base_class_2`.
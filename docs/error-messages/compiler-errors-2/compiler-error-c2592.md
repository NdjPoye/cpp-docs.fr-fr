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
ms.workload: cplusplus
ms.openlocfilehash: 3528354797987b47379d0ec56e103223ac87892f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2592"></a>Erreur du compilateur C2592
'classe' : 'base_class_2' est hérité de 'base_class_1' et ne peut pas être spécifié de nouveau  
  
 Vous ne pouvez spécifier que les classes de base qui n'héritent pas d'autres classes de base. Dans ce cas, seul `base_class_1` est nécessaire dans la spécification de `class` car `base_class_1` hérite déjà de `base_class_2`.
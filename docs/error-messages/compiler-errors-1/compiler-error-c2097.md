---
title: Erreur du compilateur C2097 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2097
dev_langs: C++
helpviewer_keywords: C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e50154d88a5019cdc181c4921c09cbd222d8b530
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2097"></a>Erreur du compilateur C2097
initialisation non conforme  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Initialisation d’une variable à l’aide d’une valeur non constante.  
  
2.  Initialisation d’une adresse courte avec une adresse longue.  
  
3.  L’initialisation d’une structure locale, une union ou un tableau avec une expression non constante lors de la compilation avec **/Za**.  
  
4.  Initialisation avec une expression contenant un opérateur virgule.  
  
5.  Initialisation avec une expression ni constante ni symbolique.
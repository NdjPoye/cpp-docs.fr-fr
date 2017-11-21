---
title: "Évaluateur d’expression, erreur CXX0069 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0069
dev_langs: C++
helpviewer_keywords: CXX0069
ms.assetid: cf334b23-1e17-4d37-acc5-18597ee84164
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1fffb675a61359913434d80fb4ab1ce11a4d6dcc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0069"></a>Évaluateur d'expression, erreur CXX0069
variable a besoin du frame de pile  
  
 L’évaluateur d’expression ne peut pas évaluer la variable, car il ne figure pas dans un frame de pile. Cela peut être dû aux variables déclarées dans le cadre d’une fonction inline.
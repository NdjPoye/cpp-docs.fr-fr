---
title: La Notation C.1 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a23b2631-8096-4bf3-ac23-ba4f4bd7a52a
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e9772b2a4b27521c7aa256f9ee7760a4687152b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="c1-notation"></a>C.1 Notation
Les règles de grammaire se composent du nom d’un non terminal, suivi du signe deux-points, suivi d’autres solutions de remplacement sur des lignes distinctes.  
  
 L’expression syntaxique termopt indique que le terme est facultatif dans le remplacement.  
  
 L’expression syntaxique *terme*optseq équivaut à *terme-seq*opt avec les règles supplémentaires suivantes :  
  
 *terme-seq* :  
  
 *terme*  
  
 *terme-seq terme*  
  
 *terme-seq* , *terme*
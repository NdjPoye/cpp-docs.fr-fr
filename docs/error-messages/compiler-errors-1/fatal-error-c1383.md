---
title: "Erreur irrécupérable C1383 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1383
dev_langs: C++
helpviewer_keywords: C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 24e9d7652c96c84f94bafbf2c808f2e5430037b2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1383"></a>Erreur irrécupérable C1383
l'option du compilateur /GL est incompatible avec la version installée du Common Language Runtime  
  
 L’erreur C1383 se produit quand vous utilisez une version précédente du Common Language Runtime avec un compilateur plus récent et quand vous compilez avec **/clr** et **/GL.**  
  
 Pour corriger, n’utilisez pas **/GL** avec **/clr** ou installez la version du Common Language Runtime fournie avec votre compilateur.  
  
 Pour plus d’informations, consultez [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) et [/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md).
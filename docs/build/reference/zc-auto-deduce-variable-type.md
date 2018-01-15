---
title: "-Zc : auto (déduire le Type de Variable) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Zc:auto
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dd2f0ff353e1243685c94da0c28f29e810b2a9ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="zcauto-deduce-variable-type"></a>/Zc:auto (déduire le type de variable)
Le **/Zc : auto [-]** option du compilateur indique au compilateur comment utiliser le [auto, mot clé](../../cpp/auto-keyword.md) pour déclarer des variables. Si vous spécifiez l’option par défaut, **/Zc : auto**, le compilateur déduit le type de la variable déclarée de son expression d’initialisation. Si vous spécifiez **/Zc:auto-**, le compilateur alloue la variable à la classe de stockage automatique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Zc:auto[-]  
```  
  
## <a name="remarks"></a>Notes  
 Le standard C++ définit une signification originale et une autre révisée pour le mot clé `auto`. Avant de [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], le mot clé déclare une variable dans la classe de stockage automatique ; autrement dit, une variable qui a une durée de vie locale. En commençant par [!INCLUDE[cpp_dev10_long](../../build/includes/cpp_dev10_long_md.md)], le mot clé déduit le type d’une variable à partir de l’expression d’initialisation de la déclaration. Utilisez le **/Zc : auto [-]** option du compilateur pour indiquer au compilateur d’utiliser la signification originale ou modifiée de la `auto` (mot clé).  
  
 Le compilateur émet un message de diagnostic approprié si votre usage du mot clé `auto` contredit l'option de compilateur actuelle. Pour plus d’informations, consultez [auto, mot clé](../../cpp/auto-keyword.md). Pour plus d’informations sur les problèmes de conformité avec Visual C++, consultez [comportement non standard](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-visual-studio"></a>Pour définir cette option de compilateur dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **propriétés de Configuration** nœud.  
  
3.  Cliquez sur le **C/C++** nœud.  
  
4.  Cliquez sur le **ligne de commande** nœud.  
  
5.  Ajouter **/Zc : auto** ou **/Zc:auto-** à la **des options supplémentaires :** volet.  
  
## <a name="see-also"></a>Voir aussi  
 [/Zc (conformité)](../../build/reference/zc-conformance.md)   
 [auto, mot clé](../../cpp/auto-keyword.md)
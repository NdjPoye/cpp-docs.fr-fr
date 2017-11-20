---
title: Robustesse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.runtime
dev_langs: C++
helpviewer_keywords: robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 27412403fe6ce0f1884a2ea99790376acb1c5236
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="robustness"></a>Robustesse
Les fonctions suivantes de la bibliothèque Runtime C permettent d'améliorer la robustesse de votre programme.  
  
### <a name="run-time-robustness-functions"></a>Fonctions de robustesse à l'exécution  
  
|Fonction|Utilisation|  
|--------------|---------|  
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Transfère le contrôle à votre mécanisme de gestion des erreurs si l'opérateur `new` ne peut pas allouer de mémoire.|  
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Gère les exceptions Win32 (exceptions structurées par C) en tant qu'exceptions typées C++.|  
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Installe votre propre fonction d’arrêt qui doit être appelée par [terminate](../c-runtime-library/reference/terminate-crt.md).|  
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Installe votre propre fonction d’arrêt qui doit être appelée par [unexpected](../c-runtime-library/reference/unexpected-crt.md).|  
  
## <a name="see-also"></a>Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [SetUnhandledExceptionFilter](http://msdn.microsoft.com/library/windows/desktop/ms680634.aspx)
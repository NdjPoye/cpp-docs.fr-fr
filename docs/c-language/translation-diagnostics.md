---
title: "Translation : Diagnostics | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 10349357fa0411357b702ff48ff9407c1f5b91e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="translation-diagnostics"></a>Translation : Diagnostics
**ANSI 2.1.1.3** Comment un diagnostic est identifié  
  
 Microsoft C génère des messages d'erreur au format suivant :  
  
```  
  
filename( line-number ) : diagnostic Cnumbermessage  
```  
  
 où *filename* est le nom du fichier source dans lequel l'erreur est survenue. *line-number* correspond au numéro de ligne auquel le compilateur a détecté l'erreur. `diagnostic` est une erreur ou un avertissement. `number` est un seul nombre à quatre chiffres (précédé d'un **C**, comme indiqué dans la syntaxe) qui identifie l'erreur ou l'avertissement. `message` est un message explicatif.  
  
## <a name="see-also"></a>Voir aussi  
 [Comportement défini par l’implémentation](../c-language/implementation-defined-behavior.md)
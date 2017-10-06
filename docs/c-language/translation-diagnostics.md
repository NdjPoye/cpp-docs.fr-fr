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
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 525f8c235a4c2500b09ac37a050d4b57fadc8fb9
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

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

---
title: "Propriété du modificateur d’un accélérateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Modifier property
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 63d6a4b526fc1f2aeb2a942e682a8c7cc6f9b58c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="accelerator-modifier-property"></a>Modifier, propriété d'un accélérateur
Les éléments suivants sont des entrées valides pour la propriété Modifier dans la table d’accélérateurs.  
  
|Value|Description|  
|-----------|-----------------|  
|**Aucun**|Utilisateur appuie sur uniquement la valeur de clé. Utilisé avec les valeurs ASCII/ANSI 001 à 026, ce qui est ^ A à ^ Z (CTRL-A à CTRL-Z).|  
|**ALT**|Utilisateur doit appuyer sur la touche ALT avant la valeur de clé.|  
|**CTRL**|Utilisateur doit appuyer sur la touche CTRL ENFONCÉE avant que la valeur de clé. Non valide avec le Type ASCII.|  
|**Touche MAJ enfoncée**|Utilisateur doit appuyer sur la touche MAJ avant la valeur de clé.|  
|**Ctrl + Alt**|Utilisateur doit appuyer sur la touche CTRL et la touche ALT avant la valeur de clé. Non valide avec le Type ASCII.|  
|**CTRL + MAJ**|Utilisateur doit appuyer sur la touche CTRL et la touche MAJ avant la valeur de clé. Non valide avec le Type ASCII.|  
|**ALT + MAJ**|Utilisateur doit appuyer sur la touche ALT et la touche MAJ avant la valeur de clé. Non valide avec le Type ASCII.|  
|**Ctrl + Alt + Maj**|Utilisateur doit appuyer sur MAJ, CTRL et ALT avant la valeur de clé. Non valide avec le Type ASCII.|  
  
## <a name="requirements"></a>Configuration requise  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des propriétés d’un accélérateur](../windows/setting-accelerator-properties.md)   
 [Éditeur d’accélérateurs](../windows/accelerator-editor.md)
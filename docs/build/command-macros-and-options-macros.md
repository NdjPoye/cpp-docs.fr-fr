---
title: "Macros de commandes et Macros d’Options | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 06f5d48395c0395a85c90096bf2dbad8627ac41a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="command-macros-and-options-macros"></a>Macros de commandes et macros d'options
Macros de commande sont prédéfinis pour les produits Microsoft. Macros d’options représentent des options de ces produits et ne sont pas définies par défaut. Les deux sont utilisés dans les règles d’inférence prédéfinies et peuvent être utilisés dans des blocs de description ou les règles d’inférence définies par l’utilisateur. Macros de commande peuvent être redéfinis pour représenter tout ou partie d’une ligne de commande, y compris les options. Macros d’options génèrent une chaîne nulle si gauche non défini.  
  
|Produit Microsoft|Macros de commande|Défini comme|Macros d’options|  
|-----------------------|-------------------|----------------|-------------------|  
|Macro Assembler|**EN TANT QUE**|ml|**AFLAGS**|  
|Compilateur Basic|**BC**|BC|**BFLAGS**|  
|Compilateur C|**CC**|CL|**CFLAGS**|  
|Compilateur C++|**CPP**|CL|**CPPFLAGS**|  
|Compilateur C++|**CXX**|CL|**CXXFLAGS**|  
|compilateur de ressources|**RC**|rc|**RFLAGS**|  
  
## <a name="see-also"></a>Voir aussi  
 [Macros spéciales de NMAKE](../build/special-nmake-macros.md)
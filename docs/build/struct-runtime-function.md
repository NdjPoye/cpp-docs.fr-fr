---
title: RUNTIME_FUNCTION, structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c05dcd516af5c078b4e4e664bae16f65370ca117
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="struct-runtimefunction"></a>RUNTIME_FUNCTION, structure
Gestion des exceptions basée sur une table requiert une entrée de table pour toutes les fonctions allouer de l’espace de pile ou d’appeler une autre fonction (par exemple, les fonctions non-feuille). Entrées de la table (fonction) ont le format suivant :  
  
|||  
|-|-|  
|ULONG|Adresse de début (fonction)|  
|ULONG|Adresse de fin (fonction)|  
|ULONG|Adresse des informations de déroulement|  
  
 La structure RUNTIME_FUNCTION doit être DWORD aligné en mémoire. Toutes les adresses sont relatives à l’image, autrement dit, ils sont des décalages de 32 bits à partir de l’adresse de départ de l’image qui contient l’entrée de fonction table. Ces entrées sont triées et placées dans la section .pdata d’une image PE32 +. Pour les fonctions générées dynamiquement [compilateurs JIT], le runtime pour prendre en charge ces fonctions doit utiliser RtlInstallFunctionTableCallback ou RtlAddFunctionTable pour fournir ces informations pour le système d’exploitation. Cela entraîne non fiable gestion des exceptions et débogage de processus.  
  
## <a name="see-also"></a>Voir aussi  
 [Données de déroulement pour la gestion des exceptions et la prise en charge du débogueur](../build/unwind-data-for-exception-handling-debugger-support.md)
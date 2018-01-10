---
title: Erreur ML non fatale A2096 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A2096
dev_langs: C++
helpviewer_keywords: A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d4466d87e33068b10b3f620bfbe764e4aec76c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ml-nonfatal-error-a2096"></a>Erreur ML non fatale A2096
**segment, groupe ou un Registre de segment attendu**  
  
 Un segment ou un groupe était attendu mais n’a été trouvé.  
  
 Une des conditions suivantes s’est produite :  
  
-   L’opérande de gauche spécifiée avec le segment remplacent l’opérateur (**:**) n’était pas un segment historique (CS, DS, SS, ES, FS ou GS), nom du groupe, nom du segment ou expression de segment.  
  
-   Le [SUPPOSÉ](../../assembler/masm/assume.md) la directive a été attribuée à un Registre de segment sans une adresse valide de segment, Registre de segment, groupe ou spéciale **plat** groupe.  
  
## <a name="see-also"></a>Voir aussi  
 [Messages d’erreur ML](../../assembler/masm/ml-error-messages.md)
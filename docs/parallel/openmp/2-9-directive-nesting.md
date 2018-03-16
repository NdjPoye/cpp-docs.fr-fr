---
title: 2.9 imbrication | Documents Microsoft
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
ms.assetid: 6565a43c-fd2d-4366-8322-8d75e1b06600
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd3c4f790681b1b044f435c03d185585b565eb62
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="29-directive-nesting"></a>2.9 Imbrication de directives
L’imbrication de directives dynamique doit respecter les règles suivantes :  
  
-   A **parallèles** directive dynamiquement à l’intérieur d’un autre **parallèles** logiquement établit une nouvelle équipe, qui est constituée du thread actuel uniquement, à moins qu’imbriqués de parallélisme est activée.  
  
-   **pour**, **sections**, et **unique** directives qui lient à la même **parallèles** ne sont pas autorisés à être imbriqués les uns des autres.  
  
-   **critique** directives portant le même nom ne sont pas autorisés à être imbriqués les uns des autres. Notez que cette restriction n’est pas suffisante pour empêcher tout interblocage.  
  
-   **pour**, **sections**, et **unique** directives ne sont pas autorisés dans l’étendue dynamique de **critique**, **classés**, et **master** régions si les directives de lier à la même **parallèles** en tant que les régions.  
  
-   **BARRIÈRE** directives ne sont pas autorisés dans l’étendue dynamique de **pour**, **classés**, **sections**, **unique**, **master**, et **critique** régions si les directives de lier à la même **parallèles** en tant que les régions.  
  
-   **maître** directives ne sont pas autorisés dans l’étendue dynamique de **pour**, **sections**, et **unique** directives si le **master** directives lier à la même **parallèles** en tant que les directives de partage de travail.  
  
-   **classés** directives ne sont pas autorisés dans l’étendue dynamique de **critique** régions si les directives de lier à la même **parallèles** en tant que les régions.  
  
-   Aucune directive est autorisé lors de l’exécution dynamiquement à l’intérieur d’une région parallèle est également autorisé lors de l’exécution en dehors d’une région parallèle. Lors de l’exécution dynamiquement en dehors d’une région parallèle spécifié par l’utilisateur, la directive est exécutée par une équipe composée d’uniquement sur le thread principal.
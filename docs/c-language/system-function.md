---
title: Fonction system | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 965cca807ddbe9f0eb31144f75a7e3c6e4a80e77
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="system-function"></a>system (fonction)
**ANSI 4.10.4.5** Contenu et mode d'exécution de la chaîne par la fonction **system**  
  
 La fonction **system** exécute une commande interne du système d'exploitation ou un fichier .EXE, .COM (.CMD sur Windows NT) ou .BAT à partir d'un programme C plutôt que de la ligne de commande.  
  
 La fonction system recherche l'interpréteur de commandes (généralement CMD.EXE dans le système d'exploitation Windows NT ou COMMAND.COM dans Windows). La fonction system passe ensuite la chaîne d’arguments à l’interpréteur de commandes.  
  
 Pour plus d'informations, voir [system, _wsystem](../c-runtime-library/reference/system-wsystem.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions des bibliothèques](../c-language/library-functions.md)
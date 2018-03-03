---
title: "PRJ0002 d’erreur de Build de projet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0002
dev_langs:
- C++
helpviewer_keywords:
- PRJ0002
ms.assetid: 1c820b1f-9a24-4681-80ed-4fcbfd7caa00
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81d7f45fb2145d0f47716841a50c9320fd46833c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0002"></a>Erreur de génération de projet PRJ0002
résultat d’erreur retourné à partir de la ligne de commande'.  
  
 Une commande, ***ligne de commande***, ce qui a été formé à partir de l’entrée d’utilisateur dans le **Pages de propriétés** , retourné un code d’erreur, mais aucune information n’apparaît dans la fenêtre Sortie.  
  
 La résolution de cette erreur dépend de l’outil ayant généré l’erreur. Pour MIDL, vous obtenez une idée de la cause du problème si /o (redirection de sortie) est définie.  
  
 Un fichier de commandes, tel qu’une étape de génération personnalisée ou un événement de build, qui n’est pas d’information sur les conditions d’échec peut également être la raison de cette erreur.
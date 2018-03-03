---
title: Erreur PRJ0008 de Build de projet | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0008
dev_langs:
- C++
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1740b0cf1edfc90258de4fe26478298ddf2875c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0008"></a>Erreur de génération de projet PRJ0008
Impossible de supprimer le fichier 'fichier'.  
  
 **Assurez-vous que le fichier n’est pas ouvert par un autre processus et qu’il n’est pas protégé en écriture.**  
  
 Lors d’une reconstruction ou de nettoyage, Visual C++ supprime tous les fichiers intermédiaires et de sortie connus de la génération, ainsi que tous les fichiers qui répondent aux spécifications de caractères génériques dans le **Extensions à supprimer lors du nettoyage** propriété dans le [général Page de propriétés de paramètres de configuration](../../ide/general-property-page-project.md).  
  
 Vous recevez cette erreur si Visual C++ n’est pas en mesure de supprimer un fichier. Pour résoudre l’erreur, vérifiez le fichier et son répertoire accessible en écriture pour l’utilisateur d’effectuer la génération.
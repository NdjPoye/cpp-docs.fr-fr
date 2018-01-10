---
title: "Erreur irrécupérable NMAKE U1059 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1059
dev_langs: C++
helpviewer_keywords: U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fb9ba98b0f82c158e4e11859e85af72efdbbc244
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1059"></a>Erreur irrécupérable NMAKE U1059
Erreur de syntaxe : '}' manquant dans le fichier dépendant  
  
 Un chemin de recherche pour une dépendance a été incorrectement spécifié. Soit un espace se trouvait dans le chemin d’accès ou l’accolade fermante (**}**) a été omis.  
  
 La syntaxe pour une spécification de répertoire d’un dépendant est  
  
 **{**   
 ***répertoires* } dépendant**  
  
 où `directories` spécifie un ou plusieurs chemins d’accès, chacun étant séparés par un point-virgule (**;**). Aucun des espaces ne sont autorisés.  
  
 Si tout ou partie d’un chemin de recherche est remplacé par une macro, assurez-vous que sans espaces existent dans l’expansion macro.
---
title: "Erreur irrécupérable RC1015 du compilateur de ressources | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC1015
dev_langs:
- C++
helpviewer_keywords:
- RC1015
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 666221cf5c3e812cd856271ea97cf4966383ec20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1015"></a>Erreur irrécupérable RC1015 du compilateur de ressources 
ne peut pas ouvrir le fichier 'nom_fichier' include  
  
 Le fichier include spécifié n’existe pas, ne peut pas être ouvert ou n’a été trouvé.  
  
 Vérifiez que les paramètres d’environnement sont valides et que le chemin du fichier est spécifié et correct. Assurez-vous que les descripteurs de fichiers suffisantes sont disponibles pour le compilateur de ressources. Si le fichier se trouve sur un lecteur réseau, assurez-vous que vous disposez des autorisations pour ouvrir le fichier.  
  
 RC1015 peut se produire même si le fichier include existe dans un répertoire spécifié comme autre répertoire inclus dans les propriétés de Configuration -> ressources -> page de propriétés Général ; Spécifiez le chemin d’accès complet au fichier include.  
  
 Pour plus d’informations, consultez l’article de la Base de connaissances Q326987 : RC1015 erreur lorsque à l’aide de ressource affichage si le chemin d’accès Include est trop Long.
---
title: "Erreur irrécupérable C1902 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1902
dev_langs:
- C++
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 89354565f67c8704eee8c8b5f9dcb94523800c63
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1902"></a>Erreur irrécupérable C1902
incompatibilité de gestionnaire de base de données de programme ; Veuillez vérifier votre installation  
  
Un fichier de base de données de programme (.pdb) a été créé à l’aide d’une version plus récente de mspdb*XXX*.dll que celui que le compilateur a trouvé sur votre système. Cette erreur indique habituellement que mspdbsrv.exe ou mspdbcore.dll sont manquants ou ont des versions différentes de mspdb*XXX*.dll. (Le *XXX* espace réservé dans le mspdb*XXX*nom de fichier .dll change avec chaque version du produit. Par exemple, dans Visual Studio 2015, le nom de fichier est mspdb140.dll.)  
  
Vérifiez les versions correspondantes de mspdbsrv.exe, mspdbcore.dll et mspdb*XXX*.dll sont installés sur votre système. Assurez-vous que les versions incompatibles n’ont pas été copiées vers le répertoire qui contient les outils du compilateur et des liens pour votre plateforme cible. Par exemple, vous pourrez avoir copié les fichiers afin de vous pouvez appeler le compilateur ou l’outil link à partir de l’invite de commandes sans définir la **chemin d’accès** variable d’environnement en conséquence.

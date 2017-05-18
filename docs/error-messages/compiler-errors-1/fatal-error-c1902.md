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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: 79987719614dfa3075f9a9090ca1d97f6546ceb3
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1902"></a>Erreur irrécupérable C1902
incompatibilité de gestionnaire de base de données de programme ; Veuillez vérifier votre installation  
  
Un fichier de base de données de programme (.pdb) a été créé à l’aide d’une version plus récente de mspdb*XXX*.dll que celui que le compilateur a trouvé sur votre système. Cette erreur indique habituellement que mspdbsrv.exe ou mspdbcore.dll sont manquants ou ont des versions différentes de mspdb*XXX*.dll. (Le *XXX* espace réservé dans le mspdb*XXX*nom de fichier .dll change avec chaque version du produit. Par exemple, dans Visual Studio 2015, le nom de fichier est mspdb140.dll.)  
  
Vérifiez les versions correspondantes de mspdbsrv.exe, mspdbcore.dll et mspdb*XXX*.dll sont installées sur votre système. Assurez-vous que les versions incompatibles n’ont pas été copiées dans le répertoire qui contient les compilateur et les outils link pour votre plateforme cible. Par exemple, vous pouvez avoir copié les fichiers afin de vous pouvez appeler l’outil du compilateur ou un lien à partir de l’invite de commandes sans définir la **chemin d’accès** variable d’environnement en conséquence.

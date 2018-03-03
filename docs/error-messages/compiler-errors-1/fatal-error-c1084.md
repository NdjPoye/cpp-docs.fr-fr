---
title: "Erreur irrécupérable C1084 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1084
dev_langs:
- C++
helpviewer_keywords:
- C1084
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 828486ee2d3057c4d9c658defc1477de49b6cd0e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1084"></a>Erreur irrécupérable C1084
Impossible de lire le fichier 'TypeFichier' : 'fichier' : message  
  
 Cette erreur résulte généralement de l'échec d'un appel à une API système interne effectué par le compilateur. Le message affiché lorsque cette erreur se produit est souvent généré par le [_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) ou [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351.aspx).  
  
 La procédure ci-dessous peut aider à résoudre l'erreur C1084 :  
  
-   Assurez-vous que le fichier spécifié existe.  
  
-   Assurez-vous que les autorisations appropriées sont définies afin de pouvoir accéder au fichier spécifié.  
  
-   Vérifiez que la syntaxe de ligne de commande respecte les règles détaillées dans [syntaxe de ligne de commande du compilateur](../../build/reference/compiler-command-line-syntax.md).  
  
-   Assurez-vous que les variables d’environnement **TMP** et **TEMP** sont correctement ensemble, ainsi que les autorisations appropriées pour accéder à ces variables d’environnement font référence aux répertoires. Vérifiez que les lecteurs référencés par le **TMP** et **TEMP** variables d’environnement contiennent une quantité adéquate d’espace libre.  
  
-   Si le message indique « numéro de fichier incorrect », le fichier spécifié était peut-être en cours de fermeture au premier plan alors que la compilation se déroulait en arrière-plan.  
  
 Après avoir effectué les diagnostics ci-dessus, effectuez un nettoyage de build.
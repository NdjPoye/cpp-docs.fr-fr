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
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: caf1e64e91871087c9e47860a41c2824a811295a
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

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

---
title: Erreur BSCMAKE BK1513 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1513
dev_langs: C++
helpviewer_keywords: BK1513
ms.assetid: 9ba87c09-8d82-4c80-b0cf-a8de63dcf9da
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3111d6823ed439aa9b26aead84c76de6bc403f9f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-error-bk1513"></a>Erreur BSCMAKE BK1513
une mise à jour non incrémentielle nécessite tous les fichiers .SBR  
  
 BSCMAKE ne peut pas générer un nouveau fichier d'informations de consultation (.bsc), car un ou plusieurs fichiers .sbr sont tronqués. Pour rechercher les noms des fichiers .sbr tronqués, lisez les [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) avertissements qui accompagnent cette erreur.  
  
 BSCMAKE peut mettre à jour un fichier .bsc avec un fichier .sbr tronqué, mais ne peut pas en générer un nouveau. BSCMAKE peut générer un nouveau fichier .bsc dans les cas suivants :  
  
-   Fichier .bsc manquant.  
  
-   Nom de fichier incorrect spécifié pour un fichier .bsc.  
  
-   Fichier .bsc endommagé.  
  
 Pour résoudre ce problème, supprimez les fichiers .sbr tronqués et procédez à une régénération, ou nettoyez la solution et procédez à une régénération. (Dans l’IDE, choisissez **générer**, **nettoyer la Solution**, puis choisissez **générer**, **régénérer la Solution**.)
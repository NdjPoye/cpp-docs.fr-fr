---
title: "Comment le contrôle de compte d’utilisateur (UAC) affecte votre Application | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- UAC [C++]
- security [C++], User Account Control
- user accounts [C++]
- User Account Control [C++]
ms.assetid: 0d001870-253e-4989-b689-f78035953799
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e609c16d63974506a06d6ec553cf4be09509acb9
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/03/2018
---
# <a name="how-user-account-control-uac-affects-your-application"></a>Répercussions du contrôle de compte utilisateur sur votre application
Le contrôle de compte d’utilisateur (UAC) est une fonctionnalité de Windows Vista dans laquelle les comptes d’utilisateurs ont des privilèges limités. Vous pouvez rechercher des informations détaillées concernant le contrôle de compte d'utilisateur sur les sites Web suivants :  
  
-   [Guide étape par étape contrôle de compte utilisateur Windows Vista](http://go.microsoft.com/fwlink/p/?linkid=53781)  
  
-   [Pratiques recommandées et des recommandations pour les Applications dans un environnement disposant de privilèges minimum](http://go.microsoft.com/fwlink/p/?linkid=82444)  
  
-   [Comprendre et configurer le contrôle de compte d’utilisateur dans Windows Vista](http://go.microsoft.com/fwlink/p/?linkid=82445)  
  
## <a name="building-projects-after-enabling-uac"></a>Génération de projets après l'activation du contrôle de compte d'utilisateur  
 Si vous générez un projet Visual C++ sur Windows Vista avec le contrôle de compte d'utilisateur désactivé et que vous activez ultérieurement le contrôle de compte d'utilisateur, vous devez nettoyer et régénérer le projet pour qu'il fonctionne correctement.  
  
## <a name="applications-that-require-administrative-privileges"></a>Applications qui requièrent des privilèges d'administrateur  
 Par défaut, l'éditeur de liens Visual C++ incorpore un fragment du contrôle de compte d'utilisateur dans le manifeste d'une application avec un niveau d'exécution `asInvoker`. Si votre application nécessite des privilèges d'administrateur pour s'exécuter correctement (par exemple, si elle modifie le nœud HKLM du Registre ou si elle écrit dans des zones protégées du disque, comme le répertoire Windows), vous devez modifier votre application.  
  
 La première option consiste à modifier le fragment du contrôle du manifeste pour modifier le niveau d’exécution pour *requireAdministrator*. L'application demande ensuite à l'utilisateur ses informations d'identification administratives avant de s'exécuter. Pour plus d’informations sur la procédure à suivre, consultez [/MANIFESTUAC (informations incorpore un compte d’utilisateur dans le manifeste)](../build/reference/manifestuac-embeds-uac-information-in-manifest.md).  
  
 La deuxième option consiste à ne pas incorporer un fragment du contrôle dans le manifeste en spécifiant le **: no** option de l’éditeur de liens. Dans ce cas, votre application s'exécutera en mode virtualisé. Toute modification apportée au Registre ou au système de fichiers ne sera pas rendue persistante une fois que votre application est terminée.  
  
 L'organigramme suivant décrit comment votre application s'exécutera selon que le contrôle de compte d'utilisateur est activé et que l'application a un manifeste de contrôle de compte d'utilisateur ou pas :  
  
 ![Comportement du chargeur de Windows Vista](media/uacflowchart.png "UACflowchart")  
  
## <a name="see-also"></a>Voir aussi  
 [Bonnes pratiques de sécurité](security-best-practices-for-cpp.md)
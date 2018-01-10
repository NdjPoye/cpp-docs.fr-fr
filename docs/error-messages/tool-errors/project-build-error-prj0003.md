---
title: "PRJ0003 d’erreur de Build de projet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0003
dev_langs: C++
helpviewer_keywords: PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bcf80eb4d45fe1ae163772b96339c123996ae377
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/03/2018
---
# <a name="project-build-error-prj0003"></a>Erreur de génération de projet PRJ0003  
  
> Génération de l’erreur '*ligne de commande*'.  
  
Le *ligne de commande* commande formée à partir de l’entrée dans le **Pages de propriétés** boîte de dialogue a retourné un code d’erreur, mais aucune information n’apparaît dans le **sortie** fenêtre.  

Les raisons possibles de cette erreur sont les suivantes :  
  
-   Votre projet dépend d’ATL Server. À compter de Visual Studio 2008, ATL Server n’est plus inclus dans le cadre de Visual Studio, mais a été publié en tant qu’un projet source partagé sur CodePlex. Pour télécharger les outils et le code source ATL Server, accédez à [outils et la bibliothèque ATL Server](http://go.microsoft.com/fwlink/p/?linkid=81979).  
  
-   Ressources système faibles. Fermez certaines applications pour résoudre ce problème.  
  
-   Privilèges de sécurité insuffisantes. Vérifiez que vous disposez des privilèges de sécurité suffisants.  
  
-   Les chemins d’accès à l’exécutables spécifiés dans **répertoires VC ++** n’incluent pas le chemin d’accès de l’outil que vous essayez d’exécuter. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md)  
  
-   Pour les projets makefile, il manque une commande à exécuter sur **générer la ligne de commande** ou **ligne de commande Rebuild**.  
  
## <a name="see-also"></a>Voir aussi  
 [Erreurs et avertissements de génération de projet (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)
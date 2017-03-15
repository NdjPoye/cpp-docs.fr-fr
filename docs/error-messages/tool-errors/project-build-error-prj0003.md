---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0003 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0003"
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur de g&#233;n&#233;ration de projet PRJ0003
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erreur lors de la génération dynamique 'ligne de commande'.  
  
 Une commande, ***ligne de commande***, formée à partir de l'entrée effectuée par l'utilisateur dans la boîte de dialogue **Pages de propriétés**, a retourné un code d'erreur, mais aucune information n'apparaît dans la fenêtre Sortie.  
  
 Les raisons possibles de cette erreur sont les suivantes :  
  
-   Votre projet dépend d'ATL Server.  À partir de [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)], ATL Server n'est plus inclus dans le cadre de Visual Studio, mais figure en tant que projet de source partagée sur CodePlex.  Pour télécharger le code source et les outils d'ATL Server, accédez à [http:\/\/go.microsoft.com\/fwlink\/?LinkID\=81979](http://go.microsoft.com/fwlink/?LinkID=81979).  
  
-   Ressources système insuffisantes.  Pour remédier à cette situation, fermez certaines applications.  
  
-   Privilèges de sécurité insuffisants.  Vérifiez que vous disposez de privilèges de sécurité suffisants.  
  
-   Les chemins de fichiers exécutables spécifiés dans les [répertoires de VC\+\+](http://msdn.microsoft.com/fr-fr/e027448b-c811-4c3d-8531-4325ad3f6e02) n'incluent pas le chemin de l'outil que vous tentez d'utiliser.  
  
-   Pour les projets Makefile, une commande est manquante sur **Ligne de commande Build** ou **Ligne de commande Rebuild**.  
  
## Voir aussi  
 [Erreurs et avertissements de génération de projet \(PRJxxxx\)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)
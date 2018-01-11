---
title: "Dépannage des personnalisations de la Build | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- build events [C++], troubleshooting
- builds [C++], build events
- troubleshooting [C++], builds
- build steps [C++], troubleshooting
- events [C++], build
- builds [C++], troubleshooting
- custom build steps [C++], troubleshooting
ms.assetid: e4ceb177-fbee-4ed3-a7d7-80f0d78c1d07
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5fa3b2d3910a71d189f5177e13fbd91930e15ee8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="troubleshooting-build-customizations"></a>Dépannage des personnalisations de génération
Si vos étapes de génération ou les événements ne sont comportent pas comme prévu, il existe plusieurs possibilités pour essayer de comprendre ce qui ne va pas.  
  
-   Assurez-vous que les fichiers que vos étapes de génération personnalisée génèrent correspondent aux fichiers que vous déclarez comme sorties.  
  
-   Si vos étapes de génération personnalisée génèrent des fichiers qui sont des entrées ou des dépendances d’autres étapes (personnalisées ou autres) de génération, assurez-vous que ces fichiers sont ajoutés à votre projet. Et vous assurer que les outils qui consomment ces fichiers s’exécutent après l’étape de génération personnalisée.  
  
-   Pour afficher ce que votre étape de génération personnalisée est en fait, ajoutez `@echo on` en tant que la première commande. Les événements et les étapes de génération sont placés dans un fichier .bat temporaire et s’exécutent lorsque le projet est généré. Par conséquent, vous pouvez ajouter la vérification des erreurs à votre événement de build ou les commandes de l’étape de génération.  
  
-   Examinez le journal de génération dans le répertoire des fichiers intermédiaires pour voir ce qui est réellement exécuté. Le chemin d’accès et le nom du journal de génération est représenté par le **MSBuild** expression de la macro, **$ (IntDir)\\$(MSBuildProjectName) .log**.  
  
-   Modifier les paramètres du projet pour collecter davantage que la quantité par défaut des informations dans le journal de génération. Dans le menu **Outils** , cliquez sur **Options**. Dans le **Options** boîte de dialogue, cliquez sur le **projets et Solutions** nœud, puis cliquez sur le **générer et exécuter** nœud. Puis, dans le **commentaires du fichier journal MSBuild project build** , cliquez sur **Detailed**.  
  
-   Vérifiez que les valeurs de n’importe quel fichier que vous utilisez des macros de nom ou de répertoire. Vous pouvez répercuter des macros individuellement, ou vous pouvez ajouter `copy %0 command.bat` au début de l’étape de génération personnalisée, qui copiera les commandes de votre étape de génération personnalisée vers command.bat avec toutes les macros sont développées.  
  
-   Exécutez les étapes de génération personnalisée et générer des événements individuellement afin de vérifier leur comportement.  
  
## <a name="see-also"></a>Voir aussi  
 [Présentation des étapes de génération personnalisée et des événements de build](../ide/understanding-custom-build-steps-and-build-events.md)
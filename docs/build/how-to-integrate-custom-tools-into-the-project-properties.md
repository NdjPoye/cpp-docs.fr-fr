---
title: "Comment&#160;: int&#233;grer les outils personnalis&#233;s dans les propri&#233;t&#233;s du projet | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.howto.integratecustomtools"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MSBuild (C++), comment : intégrer des outils personnalisés"
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Comment&#160;: int&#233;grer les outils personnalis&#233;s dans les propri&#233;t&#233;s du projet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez ajouter des options d'outils personnalisés à la fenêtre Visual Studio **Pages de propriétés** en créant un fichier de schéma XML sous\-jacent.  
  
 La section **Propriétés de configuration** de la fenêtre **Pages de propriétés** affiche des groupes de paramètres également appelés *règles*.  Chaque règle contient les paramètres d'un outil ou d'un groupe de fonctionnalités.  Par exemple, la règle **Éditeur de liens** contient les paramètres de l'outil Éditeur de liens.  Les paramètres d'une règle peuvent être subdivisés en *catégories*.  
  
 Ce document montre comment créer un fichier dans un répertoire défini qui contient les propriétés de votre outil personnalisé, de sorte que ces propriétés soient chargées au démarrage de Visual Studio.  Pour plus d'informations sur la modification du fichier, consultez [Extensibilité de plateforme : partie 2 \(page éventuellement en anglais\)](http://go.microsoft.com/fwlink/?LinkID=191489) sur le blog de l'équipe de projet Visual Studio.  
  
### Pour ajouter ou modifier des propriétés de projet  
  
1.  Dans l'Éditeur XML, créez un fichier XML.  
  
2.  Enregistrez le fichier dans le dossier %ProgramFiles%\\MSBuild\\Microsoft.Cpp\\v4.0\\.  Chaque règle de la fenêtre **Pages de propriétés** est représentée par un fichier XML dans ce dossier.  Assurez\-vous que le fichier est nommé de manière unique dans le dossier.  
  
3.  Copiez le contenu de %ProgramFiles%\\MSBuild\\Microsoft.Cpp\\v4.0\\cl.xml, fermez\-le sans enregistrer les modifications, puis collez le contenu dans votre nouveau fichier XML.  Vous pouvez utiliser n'importe quel fichier de schéma XML. Il s'agit simplement d'un fichier qui peut être utilisé comme modèle de démarrage.  
  
4.  Dans le nouveau fichier XML, modifiez le contenu en fonction de vos besoins.  Veillez à remplacer **Rule Name** et **Rule.DisplayName** en haut du fichier.  
  
5.  Enregistrez les modifications et fermez le fichier.  
  
6.  Les fichiers XML situés dans %ProgramFiles%\\MSBuild\\Microsoft.Cpp\\v4.0\\ sont chargés au démarrage de Visual Studio.  Par conséquent, pour tester le nouveau fichier, redémarrez Visual Studio.  
  
7.  Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur un projet, puis cliquez sur **Propriétés**.  Dans la fenêtre **Pages de propriétés**, dans le volet gauche, vérifiez qu'il y a un nouveau nœud qui porte le nom de votre règle.  
  
## Voir aussi  
 [MSBuild \(Visual C\+\+\)](../build/msbuild-visual-cpp.md)
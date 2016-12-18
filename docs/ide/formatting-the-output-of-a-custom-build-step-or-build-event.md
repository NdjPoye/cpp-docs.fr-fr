---
title: "Mise en forme de la sortie d&#39;une &#233;tape de g&#233;n&#233;ration personnalis&#233;e ou d&#39;un &#233;v&#233;nement de build | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "événements de build (C++), format de la sortie"
  - "étapes de génération (C++), format de la sortie"
  - "générations (C++), événements de build"
  - "générations (C++), étapes de génération personnalisée"
  - "étapes de génération personnalisée (C++), format de la sortie"
  - "événements (C++), build"
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Mise en forme de la sortie d&#39;une &#233;tape de g&#233;n&#233;ration personnalis&#233;e ou d&#39;un &#233;v&#233;nement de build
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si la sortie d'une étape de build personnalisée ou d'un événement de build est correctement mise en forme, les utilisateurs bénéficient des avantages suivants :  
  
-   Les avertissements et les erreurs sont comptabilisés dans la fenêtre **Sortie**.  
  
-   La sortie apparaît dans la fenêtre **Liste des tâches**.  
  
-   Un clic sur la sortie dans la fenêtre **Sortie** permet d'afficher la rubrique appropriée.  
  
-   Les opérations F1 sont activées dans la fenêtre **Liste des tâches** ou dans la fenêtre **Sortie**.  
  
 La sortie doit avoir le format suivant :  
  
 {*filename* \(*line\#* \[, *column\#*\]\) &#124; *toolname*} **:**  
  
 \[*any text*\] {**error** &#124; **warning**} *code\#\#\#\#***:** *localizable string*  
  
 \[ *any text* \]  
  
 Où :  
  
-   {*a* &#124; *b*} correspond à un choix entre *a* ou *b*.  
  
-   \[`ccc`\] correspond à une chaîne ou un paramètre optionnel.  
  
 Par exemple :  
  
 C:\\*sourcefile.cpp*\(134\) : erreur C2143 : erreur de syntaxe : ';' manquant avant '}'  
  
 LIEN : erreur irrécupérable LNK1104 : impossible d'ouvrir le fichier '*somelib.lib*'  
  
## Voir aussi  
 [Présentation des étapes de génération personnalisée et des événements de build](../ide/understanding-custom-build-steps-and-build-events.md)
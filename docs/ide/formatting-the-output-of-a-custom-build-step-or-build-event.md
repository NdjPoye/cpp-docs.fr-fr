---
title: "Mise en forme la sortie d’une étape de génération personnalisée ou un événement de Build | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- builds [C++], build events
- custom build steps [C++], output format
- events [C++], build
- build events [C++], output format
- build steps [C++], output format
- builds [C++], custom build steps
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 53720e93c7d45f1eaeb0e62749194720373bee1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>Mise en forme de la sortie d'une étape de génération personnalisée ou d'un événement de build
Si la sortie d’une étape de génération personnalisée ou un événement de build est correctement mise en forme, les utilisateurs obtiennent les avantages suivants :  
  
-   Erreurs et avertissements sont comptées dans le **sortie** fenêtre.  
  
-   La sortie apparaît dans le **liste des tâches** fenêtre.  
  
-   En cliquant sur la sortie dans le **sortie** fenêtre affiche la rubrique appropriée.  
  
-   Les opérations F1 sont activées dans le **liste des tâches** fenêtre ou **sortie** fenêtre.  
  
 Le format de la sortie doit être :  
  
 {*nom de fichier* (*line #* [, *colonne #*]) &#124; *toolname*} **:**  
  
 [*n’importe quel texte*] {**erreur** &#124; **avertissement**} *code ###***:***chaîne localisable*  
  
 [ *n’importe quel texte* ]  
  
 Où :  
  
-   {*un* &#124; *b*} est un choix entre *un* ou *b*.  
  
-   [`ccc`] est un paramètre ou une chaîne facultative.  
  
 Exemple :  
  
 C:\\*sourcefile.cpp*(134) : erreur C2143 : erreur de syntaxe : manquant ';' avant '}'  
  
 LINK : erreur irrécupérable LNK1104 : Impossible d’ouvrir le fichier '*somelib.lib*'  
  
## <a name="see-also"></a>Voir aussi  
 [Présentation des étapes de génération personnalisée et des événements de build](../ide/understanding-custom-build-steps-and-build-events.md)
---
title: "Erreur irr&#233;cup&#233;rable C1010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1010"
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur irr&#233;cup&#233;rable C1010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fin de fichier inattendue lors de la recherche d'un en\-tête précompilé.N'auriez\-vous pas oublié d'ajouter '\#include name' à votre source ?  
  
 Un fichier include spécifié par [\/Yu](../../build/reference/yu-use-precompiled-header-file.md) n'apparaît pas dans le fichier source.  Cette option est activée par défaut dans la plupart des types de projets Visual C\+\+ et "stdafx.h" est le fichier Include par défaut spécifié par cette option.  
  
 Dans l'environnement Visual Studio, utilisez l'une des méthodes suivantes pour résoudre cette erreur :  
  
-   Si vous n'utilisez pas d'en\-tête précompilé dans votre projet, affectez à la propriété **Création\/utilisation d'un en\-tête précompilé** des fichiers source la valeur **Sans utiliser les en\-têtes précompilés**.  Pour définir cette option du compilateur, procédez comme suit :  
  
    1.  Dans le volet Explorateur de solutions du projet, cliquez avec le bouton droit sur le nom du projet, puis cliquez sur **Propriétés**.  
  
    2.  Dans le volet gauche, cliquez sur le dossier **C\/C\+\+**.  
  
    3.  Cliquez sur le nœud **En\-têtes précompilés**.  
  
    4.  Dans le volet droit, cliquez sur **Création\/utilisation d'un en\-tête précompilé**, puis cliquez sur **Sans utiliser les en\-têtes précompilés**.  
  
-   Assurez\-vous que vous n'avez pas supprimé, renommé ou supprimé par inadvertance le fichier d'en\-tête \(par défaut, stdafx.h\) dans le projet actuel.  Ce fichier doit également être inclus avant tout autre code dans vos fichiers source à l'aide de **\#include "stdafx.h"**. \(Ce fichier d'en\-tête est spécifié en tant que propriété du projet **Création\/utilisation d'un en\-tête précompilé en spécifiant un nom de fichier**.\)
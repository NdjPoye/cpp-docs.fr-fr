---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0016 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0016"
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur de g&#233;n&#233;ration de projet PRJ0016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les paramètres de sécurité de l'utilisateur empêchent la création du processus.Ces paramètres sont requis pour la génération.  
  
 Vous avez ouvert une session en tant qu'utilisateur ne disposant pas des autorisations nécessaires pour créer des processus à l'aide d'un processus.  Vous devez modifier les niveaux d'autorisation de ce compte d'utilisateur ou contacter votre administrateur de compte.  
  
 Cette erreur peut également se produire si la clé de Registre suivante est définie :  
  
 \\\\HKCU\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer\\RestrictRun  
  
 Pour corriger cette erreur, supprimez la clé RestrictRun.  Si cette clé de Registre est nécessaire, ajoutez **vcspawn.exe** à la liste des entrées dans la clé.  
  
 Cette erreur peut également provenir du fait que votre paramètre de stratégie n'inclut pas VCSpawn.exe sous la clé de Registre HKEY\_CURRENT\_USER\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\RestrictRun comme programme Windows autorisé pour ce compte d'utilisateur.  
  
 Pour plus d'informations, consultez :  
  
-   L'article 324153 de la Base de connaissances, qui est disponible sur [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153).  
  
-   [Respect des paramètres de la stratégie système](http://msdn.microsoft.com/library/aa372139), section « Exécuter uniquement les applications Windows autorisées ».
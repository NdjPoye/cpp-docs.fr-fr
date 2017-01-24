---
title: "Proc&#233;dure pas &#224; pas&#160;: d&#233;ploiement d&#39;une application Visual&#160;C++ dans un dossier local de l&#39;application | Microsoft Docs"
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
  - "déployer des applications Visual C++"
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: d&#233;ploiement d&#39;une application Visual&#160;C++ dans un dossier local de l&#39;application
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit comment déployer une application Visual C\+\+ en copiant les fichiers à son dossier.  
  
## Composants requis  
  
-   Un ordinateur sur lequel Visual Studio est installé.  
  
-   Un autre ordinateur qui ne dispose pas des bibliothèques Visual C\+\+.  
  
### Pour déployer une application dans un dossier local de l'application  
  
1.  Créez et générez une application MFC en suivant les étapes de [Procédure pas à pas : déploiement d'une application Visual C\+\+ à l'aide d'un projet d'installation](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
2.  Copiez MFC et la bibliothèque appropriés de \(CRT\) de runtime C fichier\- pour l'exemple, pour une plateforme x86 et une prise en charge Unicode, la copie mfc100u.dll et le msvcr100.dll de \\Program Files\\Microsoft Visual Studio 10.0\\VC\\redist\\x86\\— puis collez\-les dans le dossier\\version finale\\dossier de votre projet MFC.  Pour plus d'informations sur d'autres fichiers que vous pouvez devoir copier, consultez [Détermination des DLL à redistribuer](../ide/determining-which-dlls-to-redistribute.md).  
  
3.  Exécutez l'application MFC sur un deuxième ordinateur qui ne dispose pas des bibliothèques Visual C\+\+.  
  
    1.  Copiez le contenu du\\\\ de version finale de dossier et collez\-les dans le dossier application sur le deuxième ordinateur.  
  
    2.  Exécutez l'application sur le deuxième ordinateur.  
  
     L'application s'exécute correctement car les bibliothèques Visual C\+\+ sont disponibles dans le dossier local de l'application.  
  
## Voir aussi  
 [Exemples de déploiement](../ide/deployment-examples.md)
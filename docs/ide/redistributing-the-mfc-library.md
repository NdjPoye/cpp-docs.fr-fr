---
title: "Redistribution de la biblioth&#232;que MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "MFC, redistribuer"
  - "redistribuer la bibliothèque MFC"
ms.assetid: 72714ce1-385e-4c1c-afa5-96b03e873866
caps.latest.revision: 32
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Redistribution de la biblioth&#232;que MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous liez dynamiquement votre application à la bibliothèque MFC, vous devez redistribuer Msvcr100.dll, car toutes les DLL MFC utilisent la version partagée de la bibliothèque runtime C \(crt\).  Vous devez également redistribuer Mfc100u.dll ou Mfc100.dll.  
  
 Si vous liez de manière statique votre application à MFC \(en d'autres termes, si vous spécifiez **Utiliser les MFC dans une bibliothèque statique** sous l'onglet **Général** de la boîte de dialogue **Pages de propriétés**\), vous n'avez pas à redistribuer Mfc100u.dll ou Mfc100.dll.  Toutefois, bien que la liaison statique puisse fonctionner pour le test et le déploiement interne des applications, il est déconseillé de l'utiliser pour redistribuer MFC.  Pour plus d'informations sur les stratégies conseillées pour le déploiement des bibliothèques Visual C\+\+, consultez [Choix d'une méthode de déploiement](../ide/choosing-a-deployment-method.md).  
  
 Si votre application utilise les classes MFC qui implémentent le contrôle WebBrowser \(par exemple [CHtmlView, classe](../mfc/reference/chtmlview-class.md) ou [CHtmlEditView Class](../mfc/reference/chtmleditview-class.md)\), nous vous recommandons d'installer également la version la plus récente de Microsoft Internet Explorer afin que l'ordinateur cible dispose des fichiers de contrôle commun les plus récents. \(Au minimum, Internet Explorer 4.0 est requis.\) Les informations relatives à l'installation des composants Internet Explorer sont disponibles dans l'« article 185375 : Comment créer un fichier EXE d'installation unique d'Internet Explorer » sur le site Web de support technique Microsoft.  
  
 Si votre application utilise les classes de bases de données MFC \(par exemple [CRecordset Class](../mfc/reference/crecordset-class.md) et [CRecordView Class](../mfc/reference/crecordview-class.md)\), vous devrez redistribuer ODBC et tous les pilotes ODBC utilisés par votre application.  Pour plus d'informations, consultez [Redistribution de fichiers de prise en charge de base de données](../ide/redistributing-database-support-files.md).  
  
 Si votre application MFC utilise les contrôles Windows Forms, vous devez redistribuer mfcmifc80.dll avec votre application.  Cette DLL est un assembly .NET signé avec un nom fort qui peut être redistribué avec une application dans son dossier local d'application ou en le déployant dans le Global Assembly Cache \(GAC\) à l'aide de l'[Gacutil.exe \(Global Assembly Cache Tool\)](../Topic/Gacutil.exe%20\(Global%20Assembly%20Cache%20Tool\).md).  
  
 Si vous redistribuez une DLL MFC, veillez à redistribuer la version commerciale et non pas la version Debug.  Les versions Debug des DLL ne sont pas redistribuables.  Les noms des versions Debug des DLL MFC se terminent par un « d », par exemple Mfc100d.dll.  
  
 Si vous modifiez les sources MFC d'une manière quelconque et régénérez ensuite la DLL MFC, vous devez renommer la DLL MFC modifiée afin qu'elle n'entre pas en conflit avec la DLL MFC incluse dans Visual Studio.  Il est déconseillé d'actualiser ou de renommer la DLL MFC.  Pour plus d'informations, consultez la note technique MFC 33.  
  
 Redistribuez MFC via VCRedist\_*architecture*.exe, en utilisant les modules de fusion installés avec Visual Studio ou en déployant la DLL MFC dans le même dossier que votre application.  Pour plus d'informations sur la redistribution de MFC, consultez [Redistribution des fichiers Visual C\+\+](../ide/redistributing-visual-cpp-files.md).  
  
## Installation de composants MFC localisés  
 Si vous décidez de localiser votre application en installant une DLL de localisation MFC, vous devez utiliser les fichiers redistribuables de fusion \(.msm\).  Par exemple, si vous voulez localiser votre application sur un ordinateur x86, vous devez fusionner Microsoft\_VC100\_MFCLOC\_x86.msm dans le package d'installation d'un ordinateur x86.  
  
 Les fichiers .msm redistribuables contiennent les DLL utilisées pour la localisation.  Il existe une DLL pour chaque langue prise en charge.  Le processus d'installation installe ces DLL dans le dossier %windir%\\system32\\ sur l'ordinateur cible.  
  
 Pour plus d'informations sur la localisation des applications MFC, consultez [TN057 : localisation des composants MFC](../mfc/tn057-localization-of-mfc-components.md) et [article 208983 : Comment utiliser les DLL de localisation MFC](http://go.microsoft.com/fwlink/?LinkId=198025) sur le site Web de support technique Microsoft.  
  
 Vous pouvez redistribuer les DLL de localisation MFC en déployant la DLL MFC dans le dossier local de votre application.  Pour plus d'informations sur la redistribution des bibliothèques Visual C\+\+, consultez [Redistribution des fichiers Visual C\+\+](../ide/redistributing-visual-cpp-files.md).  
  
## Voir aussi  
 [Redistribution des fichiers Visual C\+\+](../ide/redistributing-visual-cpp-files.md)
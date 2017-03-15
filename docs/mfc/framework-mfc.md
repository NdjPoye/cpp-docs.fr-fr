---
title: "Framework (MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "API (C++), encapsulation par MFC Win32"
  - "infrastructure de l'application (C++), à propos de l'infrastructure de l'application MFC"
  - "API Win32 encapsulée"
  - "encapsulation (C++)"
  - "encapsulation (C++), API Win32"
  - "MFC (C++), infrastructure de l'application"
  - "Win32 (C++), API (encapsulation par MFC)"
  - "API Windows (C++), encapsulation par MFC"
  - "classes wrapper, expliqué"
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Framework (MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Votre travail avec l'infrastructure de bibliothèque Microsoft Foundation Class \(MFC\) repose principalement sur certaines classes importantes et plusieurs outils Visual C\+\+.  Certaines classes encapsulent une grande partie de l'interface de programmation d'applications \(API\) Win32.  D'autres classes encapsulent les concepts des applications tels que des documents, des vues, et l'application elle\-même.  D'autres encore encapsulent des fonctionnalités OLE et des fonctionnalités d'accès aux données ODBC et DAO.  
  
 Par exemple, le concept de fenêtre de Win32 est encapsulé par la classe `CWnd`de MFC.  Autrement dit, une classe C\+\+ appelée `CWnd` encapsule ou « enveloppe » le handle `HWND` qui représente une fenêtre Windows.  De même, la classe `CDialog` encapsule les boîtes de dialogue Win32.  
  
 L'encapsulation signifie que la classe C\+\+ `CWnd`, par exemple, contient un attribut de type `HWND`, et les méthodes de la classe encapsulent les appels aux fonctions Win32 qui prennent `HWND` comme paramètre.  Les méthodes de la classe ont généralement le même nom que la fonction Win32 qu'elles encapsulent.  
  
## Dans cette section  
 [SDI et MDI](../mfc/sdi-and-mdi.md)  
  
 [Documents, vues et le Framework](../mfc/documents-views-and-the-framework.md)  
  
 [Assistants et Éditeurs de ressources](../mfc/wizards-and-the-resource-editors.md)  
  
## Dans les rubriques connexes  
 [Génération à partir du Framework](../mfc/building-on-the-framework.md)  
  
 [Méthode d'appel de votre code par le Framework](../mfc/how-the-framework-calls-your-code.md)  
  
 [CWinApp : classe d'application](../mfc/cwinapp-the-application-class.md)  
  
 [Modèles de document et processus de création de document\/vue](../mfc/document-templates-and-the-document-view-creation-process.md)  
  
 [Gestion des messages et mappages](../mfc/message-handling-and-mapping.md)  
  
 [Objets fenêtres](../mfc/window-objects.md)  
  
## Voir aussi  
 [Utilisation des classes pour l'écriture d'applications pour Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
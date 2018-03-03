---
title: Le Framework (MFC) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- encapsulation [MFC], Win32 API
- MFC, application framework
- wrapper classes [MFC], explained
- Win32 [MFC], API encapsulation by MFC
- application framework [MFC], about MFC application framework
- APIs [MFC], encapsulation by MFC Win32
- encapsulation [MFC]
- Windows API [MFC], encapsulation by MFC
- encapsulated Win32 API [MFC]
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c021b11809b3e6598e694fdaa46b7f829358e24f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="framework-mfc"></a>Framework (MFC)
Votre travail dans le cadre de la bibliothèque Microsoft Foundation classes (MFC) repose en grande partie sur quelques classes majeures et plusieurs outils Visual C++. Certaines classes encapsulent une grande partie de l’interface de programmation d’application (API) Win32. Autres classes encapsulent des concepts d’application tels que des documents, vues et l’application elle-même. D’autres encore encapsulent des fonctionnalités OLE et fonctionnalités d’accès aux données ODBC et DAO.  
  
 Par exemple, le concept de Win32 de fenêtre est encapsulé par la classe MFC `CWnd`. Autrement dit, une classe C++ appelée `CWnd` encapsule ou « enveloppe » le `HWND` handle qui représente une fenêtre Windows. De même, la classe `CDialog` encapsule les boîtes de dialogue Win32.  
  
 Encapsulation signifie que la classe C++ `CWnd`, par exemple, contient une variable membre de type `HWND`, et les fonctions membres de la classe encapsulent les appels aux fonctions Win32 qui acceptent un `HWND` en tant que paramètre. Les fonctions membres de classe ont généralement le même nom que la fonction Win32 qu’ils encapsulent.  
  
## <a name="in-this-section"></a>Dans cette section  
 [SDI et MDI](../mfc/sdi-and-mdi.md)  
  
 [Documents, vues et le Framework](../mfc/documents-views-and-the-framework.md)  
  
 [Assistants et les éditeurs de ressources](../mfc/wizards-and-the-resource-editors.md)  
  
## <a name="in-related-sections"></a>Dans les rubriques connexes  
 [Génération à partir du Framework](../mfc/building-on-the-framework.md)  
  
 [Méthode d’appel de votre code par le Framework](../mfc/how-the-framework-calls-your-code.md)  
  
 [CWinApp : classe d’application](../mfc/cwinapp-the-application-class.md)  
  
 [Modèles de document et le processus de création de Document/Vue](../mfc/document-templates-and-the-document-view-creation-process.md)  
  
 [Gestion et mappage des messages](../mfc/message-handling-and-mapping.md)  
  
 [Objets fenêtre](../mfc/window-objects.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des classes pour l’écriture d’applications pour Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)

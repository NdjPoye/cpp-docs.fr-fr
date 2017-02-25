---
title: "Informations sur l&#39;application et gestion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "applications (MFC), gérer"
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Informations sur l&#39;application et gestion
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lorsque vous écrivez une application, vous créez un objet dérivé de [CWinApp](../../mfc/reference/cwinapp-class.md).  Parfois, vous pouvez vouloir obtenir des informations sur l'objet depuis l'extérieur de l'objet dérivé `CWinApp`.  
  
 La bibliothèque MFC fournit les fonctions globales suivantes pour vous aider à accomplir ces tâches :  
  
### Fonctions d'information et de gestion de l'application  
  
|||  
|-|-|  
|[AfxBeginThread](../Topic/AfxBeginThread.md)|Crée un nouveau thread.|  
|[AfxEndThread](../Topic/AfxEndThread.md)|Arrête le thread actuel.|  
|[AfxFreeLibrary](../Topic/AfxFreeLibrary.md)|Décrémente le nombre de références du module de librairie de liens dynamiques \(DLL\) ; lorsque le nombre de références atteint zéro, le module n'est plus mappé.|  
|[AfxGetApp](../Topic/AfxGetApp.md)|Retourne un pointeur vers l'objet unique de `CWinApp` de l'application.|  
|[AfxGetAppName](../Topic/AfxGetAppName.md)|Retourne une chaîne qui contient le nom complet de l'application|  
|[AfxGetInstanceHandle](../Topic/AfxGetInstanceHandle.md)|Retourne `HINSTANCE` représentant cette instance de l'application.|  
|[AfxGetMainWnd](../Topic/AfxGetMainWnd.md)|Retourne un pointeur vers la fenêtre « master » actuelle d'une application de type OLE, ou le cadre de la fenêtre en place d'une application serveur.|  
|[AfxGetPerUserRegistration](../Topic/AfxGetPerUserRegistration.md)|Utilisez cette fonction pour déterminer si l'application redirige l'accès au Registre vers le nœud de **HKEY\_CURRENT\_USER** \(**HKCU**\).|  
|[AfxGetResourceHandle](../Topic/AfxGetResourceHandle.md)|Retourne `HINSTANCE` à la source de ressources par défaut de l'application.  Utilisez cette option pour accéder aux ressources de l'application.|  
|[AfxGetThread](../Topic/AfxGetThread.md)|Extrait un pointeur vers l'objet [CWinThread](../../mfc/reference/cwinthread-class.md) actuel.|  
|[AfxInitRichEdit](../Topic/AfxInitRichEdit.md)|Initialise le contrôle RichEdit de la version 1,0 de l'application.|  
|[AfxInitRichEdit2](../Topic/AfxInitRichEdit2.md)|Initialise la version 2,0 et ultérieure du contrôle RichEdit pour l'application.|  
|[AfxLoadLibrary](../Topic/AfxLoadLibrary.md)|Mappe un module DLL et retourne un descripteur qui peut être utilisé pour obtenir l'adresse d'une fonction DLL.|  
|[AfxRegisterClass](../Topic/AfxRegisterClass.md)|Enregistre une classe de fenêtre dans une DLL qui utilise MFC.|  
|[AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md)|Enregistre une classe fenêtre Windows pour compléter celles automatiquement enregistrées par MFC.|  
|[AfxSetPerUserRegistration](../Topic/AfxSetPerUserRegistration.md)|Définit si l'application redirige l'accès au Registre au nœud de **HKEY\_CURRENT\_USER** \(**HKCU**\).|  
|[AfxSetResourceHandle](../Topic/AfxSetResourceHandle.md)|Définit le descripteur de `HINSTANCE` où les ressources par défaut de l'application sont chargées.|  
|[AfxSocketInit](../Topic/AfxSocketInit.md)|Appelé dans une substitution de `CWinApp::InitInstance` pour initialiser le protocole Windows.|  
|[AfxWinInit](../Topic/AfxWinInit.md)|Appelée par la fonction `WinMain` fournie par MFC, lors de l'initialisation [CWinApp](../../mfc/reference/cwinapp-class.md) d'une application basée sur GUI, pour initialiser MFC.  Doit être appelé directement des applications console qui utilisent MFC.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)
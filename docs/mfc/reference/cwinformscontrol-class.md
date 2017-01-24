---
title: "CWinFormsControl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinFormsControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinFormsControl class"
  - "MFC (C++), prise en charge Windows Forms"
  - "Windows Forms (C++), MFC support"
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
caps.latest.revision: 28
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinFormsControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités de base pour l'hébergement d'un contrôle Windows Forms.  
  
## Syntaxe  
  
```  
template<class TManagedControl>  
class CWinFormsControl : public CWnd  
```  
  
#### Paramètres  
 `TManagedControl`  
 Un contrôle Windows Forms .NET Framework à afficher dans l'application MFC.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinFormsControl::CWinFormsControl](../Topic/CWinFormsControl::CWinFormsControl.md)|Crée un objet de wrapper de contrôle Windows Forms de MFC.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinFormsControl::CreateManagedControl](../Topic/CWinFormsControl::CreateManagedControl.md)|Crée un contrôle Windows Forms dans un conteneur MFC.|  
|[CWinFormsControl::GetControl](../Topic/CWinFormsControl::GetControl.md)|Extrait un pointeur vers le contrôle Windows Forms.|  
|[CWinFormsControl::GetControlHandle](../Topic/CWinFormsControl::GetControlHandle.md)|Récupère un handle au contrôle Windows Forms.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CWinFormsControl::operator \-\>](../Topic/CWinFormsControl::operator%20-%3E.md)|Remplace [CWinFormsControl::GetControl](../Topic/CWinFormsControl::GetControl.md) dans des expressions.|  
|[CWinFormsControl::operator TManagedControl^](../Topic/CWinFormsControl::operator%20TManagedControl%5E.md)|Effectue un type en tant que pointeur vers un contrôle Windows Forms.|  
  
## Notes  
 La classe d' `CWinFormsControl` fournit les fonctionnalités de base pour l'hébergement d'un contrôle Windows Forms.  
  
 Pour plus d'informations sur l'utilisation de Windows Forms, consultez l' [Utilisation d'un contrôle utilisateur Windows Form dans MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Votre code MFC ne doit pas mettre en cache les handles de fenêtre \(généralement stockées dans `m_hWnd`\).  Certaines propriétés de contrôle Windows Forms requièrent que Win32 sous\-jacent `Window` destruction et recréé à l'aide de `DestroyWindow` et `CreateWindow`.  L'implémentation Windows Forms de MFC gère les événements d' `Destroy` et d' `Create` des contrôles pour mettre à jour le membre d' `m_hWnd` .  
  
> [!NOTE]
>  L'intégration de MFC Windows Forms fonctionne uniquement dans les projets qui lient dynamiquement avec MFC \(dans lequel AFXDLL est défini\).  
  
## Configuration requise  
 **en\-tête :** afxwinforms.h  
  
## Voir aussi  
 [CWinFormsDialog Class](../../mfc/reference/cwinformsdialog-class.md)   
 [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md)
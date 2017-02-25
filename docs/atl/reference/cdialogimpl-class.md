---
title: "CDialogImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDialogImpl"
  - "ATL.CDialogImpl"
  - "ATL::CDialogImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialogImpl class"
  - "boîtes de dialogue, ATL"
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CDialogImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour créer un modal ou une boîte de dialogue non modale.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
class T,  
class TBase= CWindow   
>  
class ATL_NO_VTABLE CDialogImpl :  
public CDialogImplBaseT< TBase>  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `CDialogImpl`.  
  
 *TBase*  
 La classe de base de votre nouvelle classe.  La classe de base par défaut est [CWindow](../../atl/reference/cwindow-class.md).  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[Créer](../Topic/CDialogImpl::Create.md)|Crée une boîte de dialogue non modale.|  
|[DestroyWindow](../Topic/CDialogImpl::DestroyWindow.md)|Détruit une boîte de dialogue non modale.|  
|[DoModal](../Topic/CDialogImpl::DoModal.md)|Crée une boîte de dialogue modale.|  
|[EndDialog](../Topic/CDialogImpl::EndDialog.md)|Détruit une boîte de dialogue modale.|  
  
### Méthodes de CDialogImplBaseT  
  
|||  
|-|-|  
|[GetDialogProc](../Topic/CDialogImpl::GetDialogProc.md)|Retourne la procédure de boîte de dialogue active.|  
|[MapDialogRect](../Topic/CDialogImpl::MapDialogRect.md)|Mappe les unités de boîte de dialogue du rectangle spécifié pour examiner des unités \(pixels\).|  
|[OnFinalMessage](../Topic/CDialogImpl::OnFinalMessage.md)|Appelé après avoir reçu le dernier message, en général `WM_NCDESTROY`.|  
  
### Fonctions static  
  
|||  
|-|-|  
|[DialogProc](../Topic/CDialogImpl::DialogProc.md)|Traite les messages envoyés à la boîte de dialogue.|  
|[StartDialogProc](../Topic/CDialogImpl::StartDialogProc.md)|Appelé lorsque le premier message est reçu pour traiter les messages envoyés à la boîte de dialogue.|  
  
## Notes  
 Avec `CDialogImpl` vous pouvez créer un modal ou une boîte de dialogue non modale.  `CDialogImpl` fournit la procédure de boîte de dialogue, qui utilise la table des messages par défaut pour exécuter des messages aux gestionnaires appropriés.  
  
 Le destructeur **~CWindowImplRoot** de classe de base garantit que la fenêtre est allée avant la destruction de l'objet.  
  
 `CDialogImpl` dérive de **CDialogImplBaseT**, qui dérive de **CWindowImplRoot**.  
  
> [!NOTE]
>  Votre classe doit définir un membre d' **IDD** qui spécifie l'ID de ressource modèle de boîte de dialogue  Par exemple, l'Assistant Projet ATL ajoute automatiquement la ligne suivante à votre classe :  
  
 [!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/CPP/cdialogimpl-class_1.h)]  
  
 où `MyDlg` est **Nom court** entré dans la page **Noms** de l'assistant.  
  
|Pour plus d'informations sur le sujet suivant|Consultez|  
|---------------------------------------------------|---------------|  
|Créer des contrôles|[Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md)|  
|Utilisation des boîtes de dialogue dans ATL|[Classes de fenêtres ATL](../../atl/atl-window-classes.md)|  
|L'Assistant Projet ATL|[Création d'un projet ATL](../../atl/reference/creating-an-atl-project.md)|  
|Boîtes de dialogue|[boîtes de dialogue](http://msdn.microsoft.com/library/windows/desktop/ms632588) et sujets suivants dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]|  
  
## Configuration requise  
 **Header:** atlwin.h  
  
## Voir aussi  
 [BEGIN\_MSG\_MAP](../Topic/BEGIN_MSG_MAP.md)   
 [Class Overview](../../atl/atl-class-overview.md)
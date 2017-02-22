---
title: "CDataExchange Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDataExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataExchange class"
  - "DDV (dialog data validation)"
  - "DDV (dialog data validation), custom DDV routines"
  - "DDX (échange de données de boîtes de dialogue)"
  - "DDX (échange de données de boîtes de dialogue), between dialog and CDialog"
  - "DDX (échange de données de boîtes de dialogue), custom DDX routines"
  - "DDX (échange de données de boîtes de dialogue), direction of exchange"
  - "DDX/DDV"
  - "DDX/DDV, CDataExchange class"
  - "DDX/DDV, Technical Note 26"
  - "exchanging data between dialogs and CDialogs"
  - "m_bSaveAndValidate"
  - "valider des données, dialog box data entry"
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CDataExchange Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'échange de données de boîtes de dialogue \(DDX\) et les routines de \(DDV\) de validation des données de dialogue utilisées par Microsoft Foundation classes.  
  
## Syntaxe  
  
```  
class CDataExchange  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDataExchange::CDataExchange](../Topic/CDataExchange::CDataExchange.md)|Construit un objet `CDataExchange`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDataExchange::Fail](../Topic/CDataExchange::Fail.md)|Appelé lorsque la validation échoue.  Les réinitialise le focus au contrôle et aux précédents lève une exception.|  
|[CDataExchange::PrepareCtrl](../Topic/CDataExchange::PrepareCtrl.md)|Prépare le contrôle spécifié pour l'échange de données ou la validation.  Utilisation des contrôles de nonedit.|  
|[CDataExchange::PrepareEditCtrl](../Topic/CDataExchange::PrepareEditCtrl.md)|Prépare le contrôle d'édition spécifié pour l'échange de données ou la validation.|  
|[CDataExchange::PrepareOleCtrl](../Topic/CDataExchange::PrepareOleCtrl.md)|Prépare le contrôle OLE spécifié pour l'échange de données ou la validation.  Utilisation des contrôles de nonedit.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDataExchange::m\_bSaveAndValidate](../Topic/CDataExchange::m_bSaveAndValidate.md)|Balise pour la direction DDX et de DDV.|  
|[CDataExchange::m\_pDlgWnd](../Topic/CDataExchange::m_pDlgWnd.md)|La boîte de dialogue ou la fenêtre où l'échange de données nécessaire.|  
  
## Notes  
 `CDataExchange` n'a pas de classe de base.  
  
 Utilisez cette classe si vous écrivez des routines d'échange de données pour les types de données personnalisés ou les contrôles, ou si vous écrivez vos propres routines de validation des données.  Pour plus d'informations sur l'écriture de vos propres routines DDX et de DDV, consultez [note technique 26](../../mfc/tn026-ddx-and-ddv-routines.md).  Pour une présentation DDX et de DDV, consultez [échange de données de boîtes de dialogue et validation](../../mfc/dialog-data-exchange-and-validation.md) et le [boîtes de dialogue](../../mfc/dialog-boxes.md).  
  
 Un objet d' `CDataExchange` fournit des informations de contexte nécessaires pour que DDX et DDV ait lieu.  La balise `m_bSaveAndValidate` est **FALSE** lorsque le mécanisme DDX est utilisé pour remplir des valeurs initiales des contrôles de boîte de dialogue à partir de les données membres.  La balise `m_bSaveAndValidate` est **TRUE** lorsque le mécanisme DDX est utilisé pour définir les valeurs actuelles des contrôles de boîte de dialogue dans les données membres et lorsque DDV est utilisé pour valider les valeurs de données.  Si la validation de DDV échoue, la procédure de DDV affichera un message qui expliquent l'erreur d'entrée.  La procédure de DDV appelle ensuite **Échec** pour réinitialiser le focus sur le contrôle offensant et pour lever une exception pour arrêter le processus de validation.  
  
## Hiérarchie d'héritage  
 `CDataExchange`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [Exemple VIEWEX MFC](../../top/visual-cpp-samples.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWnd::DoDataExchange](../Topic/CWnd::DoDataExchange.md)   
 [CWnd::UpdateData](../Topic/CWnd::UpdateData.md)
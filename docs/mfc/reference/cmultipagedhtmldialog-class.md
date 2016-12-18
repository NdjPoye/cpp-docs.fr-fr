---
title: "CMultiPageDHtmlDialog Class | Microsoft Docs"
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
  - "CMultiPageDHtmlDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiPageDHtmlDialog class"
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMultiPageDHtmlDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une boîte de dialogue multipage affiche plusieurs pages HTML de manière séquentielle et gère les événements de chaque page.  
  
## Syntaxe  
  
```  
class CMultiPageDHtmlDialog : public CDHtmlDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMultiPageDHtmlDialog::CMultiPageDHtmlDialog](../Topic/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog.md)|Construit un objet dialog \(de style de l'assistant\) multipage DHTML.|  
|[CMultiPageDHtmlDialog::~CMultiPageDHtmlDialog](../Topic/CMultiPageDHtmlDialog::~CMultiPageDHtmlDialog.md)|Détruit un objet dialog multipage DHTML.|  
  
## Notes  
 Le mécanisme pour ce faire est [Table d'événements DHTML et d'URL](http://msdn.microsoft.com/fr-fr/2a7332f0-79d7-46e4-b816-0a618c46777a), qui contient [tables d'événements incorporés](../Topic/BEGIN_EMBED_DHTML_EVENT_MAP.md) pour chaque page.  
  
## Exemple  
 Cette boîte de dialogue multipage supposé trois ressources HTML qui définissent la fonctionnalité assistant simple.  La première page contient un bouton d' `Next` , le deuxième un bouton de **Préc** et d' `Next` , et le troisième un bouton de **Préc** .  Lorsqu'un des boutons est enfoncé, des appels de fonction gestionnaire [CDHtmlDialog::LoadFromResource](../Topic/CDHtmlDialog::LoadFromResource.md) pour charger la nouvelle page appropriée.  
  
 Les parties pertinentes de la déclaration de classe \(dans CMyMultiPageDlg.h\) :  
  
 [!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/CPP/cmultipagedhtmldialog-class_1.h)]  
  
 Les parties pertinentes de l'implémentation de classe \(dans CMyMultipageDlg.cpp\) :  
  
 [!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/CPP/cmultipagedhtmldialog-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)  
  
 `CMultiPageDHtmlDialog`  
  
## Configuration requise  
 **Header:** afxdhtml.h  
  
## Voir aussi  
 [CDHtmlDialog Class](../../mfc/reference/cdhtmldialog-class.md)   
 [Multipage DHTML and URL Event Maps \(NIB\)](http://msdn.microsoft.com/fr-fr/2a7332f0-79d7-46e4-b816-0a618c46777a)
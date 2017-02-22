---
title: "CMFCImageEditorDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCImageEditorDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCImageEditorDialog class"
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMFCImageEditorDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCImageEditorDialog` prend en charge une boîte de dialogue d'éditeur d'images.  
  
## Syntaxe  
  
```  
class CMFCImageEditorDialog : public CDialogEx  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCImageEditorDialog::CMFCImageEditorDialog](../Topic/CMFCImageEditorDialog::CMFCImageEditorDialog.md)|Construit un objet `CMFCImageEditorDialog`.|  
  
## Notes  
 La classe d' `CMFCImageEditorDialog` fournit une boîte de dialogue qui inclut :  
  
-   Une zone d'image que vous utilisez pour modifier pixels individuels dans une image.  
  
-   Outils de dessin pour modifier les pixels dans la zone d'image.  
  
-   Une palette de couleurs pour spécifier la couleur utilisée par les outils de dessin.  
  
-   Une zone aperçu qui affiche l'effet de votre modification.  
  
 l'illustration suivante montre une boîte de dialogue d'éditeur d'images.  
  
 ![Boîte de dialogue CMFCImageEditorDialog](../../mfc/reference/media/imageedit.png "ImageEdit")  
  
 Une façon d'utiliser un objet d' `CMFCImageEditorDialog` est de le passage d'une image d' `CBitmap` à modifier.  Ne créez pas une grande image parce que la zone d'édition d'images a une taille limitée et la taille en pixels logiques est définie à la zone.  Appelez la méthode d' `DoModal` pour démarrer une boîte de dialogue modale.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)  
  
## Configuration requise  
 **en\-tête :** afximageeditordialog.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)
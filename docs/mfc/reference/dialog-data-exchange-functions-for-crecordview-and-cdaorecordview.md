---
title: "&#201;change de donn&#233;es de bo&#238;tes de dialogue pour CRecordView et CDaoRecordView | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO (C++), échange de données de boîtes de dialogue (DDX) (prise en charge)"
  - "bases de données (C++), échange de données de boîtes de dialogue (DDX) (prise en charge)"
  - "DDX (échange de données de boîtes de dialogue) (C++), prise en charge de la base de données"
  - "DDX (échange de données de boîtes de dialogue) (C++), fonctions"
  - "DDX_Field (fonctions)"
  - "ODBC (C++), échange de données de boîtes de dialogue (DDX) (prise en charge)"
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# &#201;change de donn&#233;es de bo&#238;tes de dialogue pour CRecordView et CDaoRecordView
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique répertorie les fonctions de DDX\_Field utilisées pour échanger des données entre un [CRecordset](../../mfc/reference/crecordset-class.md) et un formulaire [CRecordView](../../mfc/reference/crecordview-class.md) ou entre un [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) et un [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).  
  
> [!NOTE]
>  Les fonctions de DDX\_Field sont semblables aux fonctions de DDX car elles échangent des données avec des contrôles dans un formulaire.  Mais contrairement à DDX, elles échangent des données avec les champs de l'objet recordset associé à la vue plutôt qu'avec les champs de la vue d'enregistrement elle\-même.  Pour plus d'informations, consultez les classes `CRecordView` et `CDaoRecordView`.  
  
### DDX\_Field Fonctions  
  
|||  
|-|-|  
|[DDX\_FieldCBIndex](../Topic/DDX_FieldCBIndex.md)|Transfère des données de type entier entre un membre de données de champ recordset et l'index de la sélection actuelle dans une zone de liste déroulante de [CRecordView](../../mfc/reference/crecordview-class.md) ou [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md).|  
|[DDX\_FieldCBString](../Topic/DDX_FieldCBString.md)|Transfère des données `CString` entre un membre de données de champ recordset et le contrôle d'édition dans la zone de liste déroulante de `CRecordView` ou `CDaoRecordView`.  Lors du déplacement de données depuis le recordset vers le contrôle, cette fonction permet de sélectionner l'élément dans la zone de liste déroulante qui commence par les caractères de la chaîne spécifiée.|  
|[DDX\_FieldCBStringExact](../Topic/DDX_FieldCBStringExact.md)|Transfère des données `CString` entre un membre de données de champ recordset et le contrôle d'édition dans la zone de liste déroulante de `CRecordView` ou `CDaoRecordView`.  Lors du déplacement de données depuis le recordset vers le contrôle, cette fonction permet de sélectionner l'élément dans la zone de liste déroulante qui correspond exactement à la chaîne spécifiée.|  
|[DDX\_FieldCheck](../Topic/DDX_FieldCheck.md)|Données booléennes de transfert entre un membre de données de champ d'ensemble d'enregistrements et une case à cocher dans `CRecordView` ou `CDaoRecordView`.|  
|[DDX\_FieldLBIndex](../Topic/DDX_FieldLBIndex.md)|Transfère des données de type entier entre un membre de données de champ recordset et l'index de la sélection actuelle dans une zone de liste dans un `CRecordView` ou un `CDaoRecordView`.|  
|[DDX\_FieldLBString](../Topic/DDX_FieldLBString.md)|Gère le transfert des données de [CString](../../atl-mfc-shared/reference/cstringt-class.md) entre un contrôle zone de liste et les données de membre de champ d'un recordset.  Lors du déplacement de données depuis le recordset vers le contrôle, cette fonction permet de sélectionner l'élément dans la zone de liste qui commence par les caractères de la chaîne spécifiée.|  
|[DDX\_FieldLBStringExact](../Topic/DDX_FieldLBStringExact.md)|Gère le transfert des données de `CString` entre un contrôle zone de liste et les données de membre de champ d'un recordset.  Lors du déplacement de données depuis le recordset vers le contrôle, cette fonction permet de sélectionner le premier élément correspondant exactement à la chaîne spécifiée.|  
|[DDX\_FieldRadio](../Topic/DDX_FieldRadio.md)|Transfère des données de type entier entre un membre de données de champ recordset et un groupe de cases d'option dans un `CRecordView` ou un `CDaoRecordView`.|  
|[DDX\_FieldScroll](../Topic/DDX_FieldScroll.md)|Fixe ou obtient la position de défilement d'un contrôle de barre de défilement dans un `CRecordView` ou un `CDaoRecordView`.  Appel de la fonction [DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md).|  
|[DDX\_FieldText](../Topic/DDX_FieldText.md)|Les versions surchargées sont disponibles pour transférer `int`, **UINT**, **long**, `DWORD`, [CString](../../atl-mfc-shared/reference/cstringt-class.md), **float**, **double**, **short**, [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md), et les données de [COleCurrency](../../mfc/reference/colecurrency-class.md) entre un membre de données de champ d'ensemble d'enregistrements et une zone d'édition dans `CRecordView` ou `CDaoRecordView`.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)
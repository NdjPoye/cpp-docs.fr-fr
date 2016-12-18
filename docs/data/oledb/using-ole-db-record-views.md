---
title: "Utilisation des vues de l&#39;enregistrement OLE&#160;DB | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "COleDBRecordView (classe), vue d'ensemble"
  - "MFC, vues des enregistrements"
  - "vues des enregistrements OLE DB"
  - "OLE DB, vues des enregistrements"
  - "vues des enregistrements, objets de vue d'enregistrement"
  - "jeux de lignes, vues des enregistrements"
ms.assetid: 1cd3e595-ce08-43d8-a0a9-d03b5d3e24ce
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation des vues de l&#39;enregistrement OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Si vous souhaitez afficher des données du jeu de lignes OLE DB dans une application MFC, vous devez utiliser la classe MFC [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md).  Un objet recordview créé à partir de `COleDBRecordView` vous permet d'afficher des enregistrements de la base de données dans des contrôles MFC.  La vue de l'enregistrement est une vue de type formulaire des boîtes de dialogue directement connectée à un objet jeu de lignes OLE DB créé à partir de la classe de modèles `CRowset`.  L'obtention d'un handle de l'objet jeu de lignes est simple :  
  
```  
COleDBRecordView myRecordView;  
...  
// CProductAccessor is a user record class  
CRowset<CAccessor<CProductAccessor>> myRowSet = myRecordView.OnGetRowset();  
```  
  
 La vue affiche les champs de l'objet `CRowset` dans les contrôles de la boîte de dialogue.  L'objet `COleDBRecordView` utilise les fonctionnalités de l'Échange de données de boîtes de dialogue \(DDX\) et de navigation intégrées à `CRowset` \(**MoveFirst**, `MoveNext`, `MovePrev` et `MoveLast`\) pour automatiser le déplacement des données entre les contrôles sur le formulaire et les champs de l'ensemble de lignes.  `COleDBRecordView` effectue le suivi de la position de l'utilisateur dans l'ensemble de lignes afin que la vue de l'enregistrement puisse mettre à jour l'interface utilisateur et fournit une méthode [OnMove](../Topic/COleDBRecordView::OnMove.md) pour la mise à jour de l'enregistrement actif avant de passer à un autre.  
  
 Vous pouvez utiliser des fonctions DDX avec **COleDbRecordView** pour obtenir des données directement du recordset de la base de données et les afficher dans un contrôle de boîte de dialogue.  Vous devez utiliser les méthodes **DDX\_\*** \(telles que `DDX_Text`\), mais pas les fonctions **DDX\_Field\*** \(telles que `DDX_FieldText`\) avec **COleDbRecordView**.  
  
## Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)   
 [COleDBRecordView Class](../../mfc/reference/coledbrecordview-class.md)
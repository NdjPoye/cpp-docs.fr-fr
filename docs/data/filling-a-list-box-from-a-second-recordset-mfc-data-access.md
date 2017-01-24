---
title: "Remplissage d&#39;une zone de liste &#224; partir d&#39;un second recordset (Acc&#232;s aux donn&#233;es MFC) | Microsoft Docs"
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
  - "CComboBox (classe), remplir un objet à partir d'un second jeu de lignes"
  - "CListCtrl (classe), remplir à partir d'un second recordset"
  - "zones de liste déroulante (C++), remplir à partir d'un second recordset"
  - "DAO (recordsets)"
  - "DAO (recordsets), remplir des zones de liste ou des zones de liste déroulante"
  - "remplir des listes ou des zones de liste déroulante"
  - "zones de liste, remplir à partir d'un second recordset"
  - "recordsets multiples dans les vues d'enregistrements"
  - "ODBC (recordsets C++), remplir des zones de liste ou des zones de liste déroulante"
  - "vues des enregistrements, remplir des zones de liste"
  - "recordsets (C++), remplir des zones de liste ou des zones de liste déroulante"
ms.assetid: 360c0834-da6b-4dc0-bcea-80e9acd611f0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Remplissage d&#39;une zone de liste &#224; partir d&#39;un second recordset (Acc&#232;s aux donn&#233;es MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Par défaut, une vue d'enregistrement est associée à un seul objet recordset dont les champs sont mappés aux contrôles de la vue d'enregistrement.  Parfois, vous souhaiterez peut\-être placer un contrôle de zone de liste ou de zone de liste déroulante dans votre vue d'enregistrement et le remplir avec des valeurs issues d'un second objet recordset.  L'utilisateur peut utiliser la zone de liste pour sélectionner une nouvelle catégorie d'informations à afficher dans la vue d'enregistrement.  Cette rubrique explique quand et comment procéder ainsi.  
  
> [!TIP]
>  Sachez que le remplissage d'une zone de liste déroulante ou zone de liste à partir d'une source de données peut être lente.  Prenez des précautions contre les tentatives de remplissage d'un contrôle à partir d'un recordset contenant un grand nombre d'enregistrements.  
  
 Le modèle pour cette rubrique se compose d'un recordset principal qui remplit les contrôles de votre formulaire, tandis qu'un recordset secondaire remplit une zone de liste ou zone de liste déroulante.  La sélection d'une chaîne dans la zone de liste fait en sorte que votre programme réinterroge le recordset principal en fonction de ce qui a été sélectionné.  La procédure suivante utilise une zone de liste déroulante, mais s'applique également à une zone de liste.  
  
#### Pour remplir une zone de liste déroulante ou une zone de liste à partir d'un second recordset  
  
1.  Créez l'objet recordset \([CRecordset](../mfc/reference/crecordset-class.md) pour ODBC, [CDaoRecordset](../mfc/reference/cdaorecordset-class.md) pour DAO\).  
  
2.  Obtenez un pointeur vers l'objet [CComboBox](../mfc/reference/ccombobox-class.md) pour le contrôle de zone de liste déroulante.  
  
3.  Videz la zone de liste déroulante de son contenu précédent.  
  
4.  Parcourez tous les enregistrements dans l'objet recordset et appelez [CComboBox::AddString](../Topic/CComboBox::AddString.md) pour chaque chaîne de l'enregistrement actif que vous souhaitez ajouter à la zone de liste déroulante.  
  
5.  Initialisez la sélection dans la zone de liste déroulante.  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
    // ...  
  
    // Fill the combo box with all of the courses  
    CENROLLDoc* pDoc = GetDocument();  
    if (!pDoc->m_courseSet.Open())  
        return;  
  
    // ...  
  
    m_ctlCourseList.ResetContent();  
    if (pDoc->m_courseSet.IsOpen())  
    {   
        while (!pDoc->m_courseSet.IsEOF() )  
        {  
            m_ctlCourseList.AddString(  
                pDoc->m_courseSet.m_CourseID);  
            pDoc->m_courseSet.MoveNext();  
        }  
    }  
    m_ctlCourseList.SetCurSel(0);  
}  
```  
  
 Cette fonction utilise un second recordset, `m_courseSet`, qui contient un enregistrement pour chaque cours proposé, et un contrôle `CComboBox`, `m_ctlCourseList`, qui est stocké dans la classe de vue d'enregistrement.  
  
 La fonction obtient `m_courseSet` à partir du document et l'ouvre.  Ensuite, elle vide `m_ctlCourseList` et parcourt `m_courseSet`.  Pour chaque enregistrement, la fonction appelle la fonction membre `AddString` de la zone de liste déroulante pour ajouter la valeur de l'ID du cours à partir de l'enregistrement.  Pour finir, le code définit la sélection de la liste déroulante.  
  
## Voir aussi  
 [Vues d'enregistrements \(Accès aux données MFC\)](../data/record-views-mfc-data-access.md)   
 [Liste de pilotes ODBC](../data/odbc/odbc-driver-list.md)
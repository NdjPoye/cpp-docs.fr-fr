---
title: "CComboBoxEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComboBoxEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComboBoxEx class"
  - "zones de liste déroulante (C++), CComboBoxEx class"
  - "common controls [C++], extended combo boxes"
  - "extended combo boxes, CComboBoxEx class"
  - "Internet Explorer 4.0 common controls"
  - "Windows common controls [C++], extended combo boxes"
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
caps.latest.revision: 26
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComboBoxEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Étend le contrôle zone de liste déroulante en fournissant la prise en charge pour les listes d'images.  
  
## Syntaxe  
  
```  
class CComboBoxEx : public CComboBox  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComboBoxEx::CComboBoxEx](../Topic/CComboBoxEx::CComboBoxEx.md)|Construit un objet `CComboBoxEx`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComboBoxEx::Create](../Topic/CComboBoxEx::Create.md)|Crée la zone de liste déroulante et la attaché à l'objet d' `CComboBoxEx` .|  
|[CComboBoxEx::CreateEx](../Topic/CComboBoxEx::CreateEx.md)|Crée une zone de liste déroulante avec les styles étendus par windows spécifiées et la attaché à un objet de **ComboBoxEx** .|  
|[CComboBoxEx::DeleteItem](../Topic/CComboBoxEx::DeleteItem.md)|Supprime un élément d'un contrôle de **ComboBoxEx** .|  
|[CComboBoxEx::GetComboBoxCtrl](../Topic/CComboBoxEx::GetComboBoxCtrl.md)|Extrait un pointeur vers le contrôle de zone de liste enfant.|  
|[CComboBoxEx::GetEditCtrl](../Topic/CComboBoxEx::GetEditCtrl.md)|Récupère le handle à la partie du contrôle d'édition d'un contrôle de **ComboBoxEx** .|  
|[CComboBoxEx::GetExtendedStyle](../Topic/CComboBoxEx::GetExtendedStyle.md)|Récupère les styles étendus en cours de utilisation pour un contrôle de **ComboBoxEx** .|  
|[CComboBoxEx::GetImageList](../Topic/CComboBoxEx::GetImageList.md)|Extrait un pointeur vers la liste d'images assignée à un contrôle de **ComboBoxEx** .|  
|[CComboBoxEx::GetItem](../Topic/CComboBoxEx::GetItem.md)|Récupère les informations d'élément pour un élément donné de **ComboBoxEx** .|  
|[CComboBoxEx::HasEditChanged](../Topic/CComboBoxEx::HasEditChanged.md)|Détermine si l'utilisateur a modifié le contenu du contrôle d'édition de **ComboBoxEx** en tapant.|  
|[CComboBoxEx::InsertItem](../Topic/CComboBoxEx::InsertItem.md)|Insère un nouvel élément dans un contrôle de **ComboBoxEx** .|  
|[CComboBoxEx::SetExtendedStyle](../Topic/CComboBoxEx::SetExtendedStyle.md)|Styles étendus par définit dans un contrôle de **ComboBoxEx** .|  
|[CComboBoxEx::SetImageList](../Topic/CComboBoxEx::SetImageList.md)|Définit une liste d'images pour un contrôle de **ComboBoxEx** .|  
|[CComboBoxEx::SetItem](../Topic/CComboBoxEx::SetItem.md)|Définit les attributs d'un élément dans un contrôle de **ComboBoxEx** .|  
|[CComboBoxEx::SetWindowTheme](../Topic/CComboBoxEx::SetWindowTheme.md)|Définit le style visuel du contrôle zone de liste déroulante étendue.|  
  
## Notes  
 À l'aide de `CComboBoxEx` pour créer des contrôles de zone de liste déroulante, vous ne devez plus implémenter votre propre code de dessin d'image.  À la place, utilisez `CComboBoxEx` d'accéder aux images d'une liste d'images.  
  
## Prise en charge de la liste d'images  
 Dans une zone de liste déroulante standard, le propriétaire de la zone de liste déroulante est chargé de dessiner une image en créant la zone de liste déroulante comme contrôle owner draw.  Lorsque vous utilisez `CComboBoxEx`, vous n'avez pas besoin de définir les styles de dessin **CBS\_OWNERDRAWFIXED** et **CBS\_HASSTRINGS** car ils sont impliqués.  Sinon, vous devez écrire le code pour exécuter des opérations de dessin.  Un contrôle d' `CComboBoxEx` prend en charge jusqu'à trois images par article : un pour un état sélectionné, un pour un état non sélectionné, et un pour une image de superposition.  
  
## Styles  
 `CComboBoxEx` prend en charge les styles **CBS\_SIMPLE**, **CBS\_DROPDOWN**, **CBS\_DROPDOWNLIST**, et **WS\_CHILD**.  Tous les autres styles sont passés lorsque vous créez la fenêtre est ignoré par le contrôle.  Une fois la fenêtre créée, vous pouvez fournir d'autres styles de zone de liste déroulante en appelant la fonction membre [SetExtendedStyle](../Topic/CComboBoxEx::SetExtendedStyle.md)d' `CComboBoxEx` .  Avec ces styles, vous pouvez :  
  
-   Définissez la recherche de chaîne dans la liste pour distinguer la casse.  
  
-   Créez un contrôle zone de liste déroulante qui utilise la barre oblique \("\/"\), la barre oblique inverse \(" \\ "\), et les caractères de le point \(". "\) comme séparateurs de mot.  Cela permet aux utilisateurs de saut de mot\-à\-mot, à l'aide de la TOUCHE de raccourci clavier CTRL\+.  
  
-   Placez le contrôle zone de liste déroulante à l'affichage ou ne pas afficher une image.  Si aucune icône n'est affichée, la zone de liste déroulante peut supprimer l'retrait de texte qui s'adapte à une image.  
  
-   Créez un contrôle zone de liste déroulante étroite, y compris le dimensionnement de lui elle fractionne la zone de liste déroulante plus large qu'il contient.  
  
 Ces indicateurs de style sont décrites plus loin dans [Utilisation CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
## Attributs de stockage et d'éléments de rappel d'élément  
 Les informations d'élément, telles que les index des éléments et des images, des valeurs de mise en retrait, et des chaînes de texte, sont stockées dans la structure [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746)Win32, comme décrit dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  La structure contient également les membres qui correspondent aux balises de rappel.  
  
 Pour une description détaillée et conceptuelle, consultez l' [Utilisation CComboBoxEx](../../mfc/using-ccomboboxex.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## Configuration requise  
 **Header:** afxcmn.h  
  
## Voir aussi  
 [MFC exemple MFCIE](../../top/visual-cpp-samples.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)
---
title: "CBitmap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBitmap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBitmap class"
  - "drawing, outils"
  - "GDI bitmap"
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CBitmap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule une bitmap de définition de données \(GDI\) Graphics Device Interface windows et fournit les fonctions membres pour manipuler la bitmap.  
  
## Syntaxe  
  
```  
class CBitmap : public CGdiObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CBitmap::CBitmap](../Topic/CBitmap::CBitmap.md)|Construit un objet `CBitmap`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CBitmap::CreateBitmap](../Topic/CBitmap::CreateBitmap.md)|Initialise l'objet avec un bitmap en mémoire du périphérique qui a une largeur, la hauteur, et un modèle binaire spécifiés.|  
|[CBitmap::CreateBitmapIndirect](../Topic/CBitmap::CreateBitmapIndirect.md)|Initialise l'objet avec une bitmap à la largeur, la hauteur, et le modèle binaire \(s'il est spécifié\) fourni dans une structure de **BITMAP** .|  
|[CBitmap::CreateCompatibleBitmap](../Topic/CBitmap::CreateCompatibleBitmap.md)|Initialise l'objet avec une bitmap pour qu'elle soit compatible avec un appareil spécifié.|  
|[CBitmap::CreateDiscardableBitmap](../Topic/CBitmap::CreateDiscardableBitmap.md)|Initialise l'objet avec une bitmap discardable compatible avec un appareil spécifié.|  
|[CBitmap::FromHandle](../Topic/CBitmap::FromHandle.md)|Retourne un pointeur vers un objet d' `CBitmap` une fois donné un handle à une bitmap d' `HBITMAP` windows.|  
|[CBitmap::GetBitmap](../Topic/CBitmap::GetBitmap.md)|Remplit la structure de **BITMAP** d'informations sur la bitmap.|  
|[CBitmap::GetBitmapBits](../Topic/CBitmap::GetBitmapBits.md)|Copie les bits de la bitmap spécifiée dans la mémoire tampon spécifiée.|  
|[CBitmap::GetBitmapDimension](../Topic/CBitmap::GetBitmapDimension.md)|Retourne la largeur et la hauteur de la bitmap.  Il est supposé que la hauteur et la largeur sont fixées précédemment par la fonction membre de [SetBitmapDimension](../Topic/CBitmap::SetBitmapDimension.md) .|  
|[CBitmap::LoadBitmap](../Topic/CBitmap::LoadBitmap.md)|Initialise l'objet en chargeant une ressource bitmap nommée du fichier exécutable de l'application et en attachant la bitmap à l'objet.|  
|[CBitmap::LoadMappedBitmap](../Topic/CBitmap::LoadMappedBitmap.md)|Charge une bitmap et les cartes couleurs aux couleurs système actuels.|  
|[CBitmap::LoadOEMBitmap](../Topic/CBitmap::LoadOEMBitmap.md)|Initialise l'objet en chargeant un bitmap Windows prédéfini et en attachant la bitmap à l'objet.|  
|[CBitmap::SetBitmapBits](../Topic/CBitmap::SetBitmapBits.md)|Définit les bits d'une bitmap aux valeurs de bits spécifié.|  
|[CBitmap::SetBitmapDimension](../Topic/CBitmap::SetBitmapDimension.md)|Assigne une largeur et la hauteur une bitmap en unités de 0,1 millimètres.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CBitmap::operator HBITMAP](../Topic/CBitmap::operator%20HBITMAP.md)|Retourne le handle de fenêtre attaché à l'objet d' `CBitmap` .|  
  
## Notes  
 Pour utiliser un objet d' `CBitmap` , construisez l'objet, attachez un handle de bitmap à avec l'une des fonctions membres d'initialisation, puis appelez les fonctions membres de l'objet.  
  
 Pour plus d'informations sur l'utilisation des objets graphiques souhaitez `CBitmap`, consultez [objets graphiques](../../mfc/graphic-objects.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBitmap`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [Exemple MDI MFC](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)
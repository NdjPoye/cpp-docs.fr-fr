---
title: "CStockPropImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStockPropImpl"
  - "ATL::CStockPropImpl"
  - "ATL.CStockPropImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [ATL], propriétés stock"
  - "CStockPropImpl class"
  - "propriétés stock, contrôles ATL"
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CStockPropImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour prendre en charge les valeurs de propriétés stock.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
class T,  
class InterfaceName,   
const IID* piid= &_ATL_IIDOF(InterfaceName),   
const GUID* plibid= &CComModule::m_libid,   
WORD wMajor= 1,  
WORD wMinor= 0,   
class tihclass= CcomTypeInfoHolder  
>  
class ATL_NO_VTABLE CStockPropImpl :  
public IDispatchImpl< InterfaceName, piid, plibid, wMajor,  
   wMinor, tihclass>  
```  
  
#### Paramètres  
 `T`  
 La classe implémentant le contrôle et dérivant de `CStockPropImpl`.  
  
 `InterfaceName`  
 Une interface double exposant des propriétés stock.  
  
 `piid`  
 Pointeur vers l'IID d' `InterfaceName`.  
  
 `plibid`  
 Pointeur vers le LIBID de la bibliothèque de types qui contient la définition d' `InterfaceName`.  
  
 `wMajor`  
 Version principale de la bibliothèque de types.  La valeur par défaut est 1.  
  
 `wMinor`  
 Version secondaire de la bibliothèque de types.  La valeur par défaut est 0.  
  
 `tihclass`  
 La classe utilisée pour gérer les informations de type pour `T`.  La valeur par défaut est `CComTypeInfoHolder`.  
  
## Membres  
  
### Méthodes publiques  
  
|||  
|-|-|  
|[get\_Appearance](../Topic/CStockPropImpl::get_Appearance.md)|Appelez cette méthode pour obtenir le style de peinture utilisé par le contrôle, par exemple, plate ou 3D.|  
|[get\_AutoSize](../Topic/CStockPropImpl::get_AutoSize.md)|Appelez cette méthode pour obtenir l'état de la balise qui indique si le contrôle ne peut pas être aucune autre taille.|  
|[get\_BackColor](../Topic/CStockPropImpl::get_BackColor.md)|Appelez cette méthode pour obtenir la couleur d'arrière\-plan du contrôle.|  
|[get\_BackStyle](../Topic/CStockPropImpl::get_BackStyle.md)|Appelez cette méthode pour obtenir le style d'arrière\-plan du contrôle, transparent ou opaque.|  
|[get\_BorderColor](../Topic/CStockPropImpl::get_BorderColor.md)|Appelez cette méthode pour obtenir la couleur de la bordure du contrôle.|  
|[get\_BorderStyle](../Topic/CStockPropImpl::get_BorderStyle.md)|Appelez cette méthode pour obtenir le style de bordure du contrôle.|  
|[get\_BorderVisible](../Topic/CStockPropImpl::get_BorderVisible.md)|Appelez cette méthode pour obtenir l'état de la balise qui indique si la bordure du contrôle est visible ou non.|  
|[get\_BorderWidth](../Topic/CStockPropImpl::get_BorderWidth.md)|Appelez cette méthode pour obtenir la largeur \(en pixels\) de la bordure du contrôle.|  
|[get\_Caption](../Topic/CStockPropImpl::get_Caption.md)|Appelez cette méthode pour obtenir le texte spécifié dans la légende d'un objet.|  
|[get\_DrawMode](../Topic/CStockPropImpl::get_DrawMode.md)|Appelez cette méthode pour obtenir le mode dessin du contrôle, par exemple, stylet de bits XOR ou pour inverser les couleurs.|  
|[get\_DrawStyle](../Topic/CStockPropImpl::get_DrawStyle.md)|Appelez cette méthode pour obtenir le style de dessin du contrôle, par exemple, unie, précipité, ou en pointillés.|  
|[get\_DrawWidth](../Topic/CStockPropImpl::get_DrawWidth.md)|Appelez cette méthode pour obtenir la largeur de dessin \(en pixels\) utilisée par les méthodes de dessin du contrôle.|  
|[get\_Enabled](../Topic/CStockPropImpl::get_Enabled.md)|Appelez cette méthode pour obtenir l'état de la balise qui indique si le contrôle est activé.|  
|[get\_FillColor](../Topic/CStockPropImpl::get_FillColor.md)|Appelez cette méthode pour obtenir la couleur de remplissage du contrôle.|  
|[get\_FillStyle](../Topic/CStockPropImpl::get_FillStyle.md)|Appelez cette méthode pour obtenir le style du remplissage du contrôle, par exemple, unie, transparents, ou l'avez contre\-haché.|  
|[get\_Font](../Topic/CStockPropImpl::get_Font.md)|Appelez cette méthode pour obtenir un pointeur vers les propriétés de police du contrôle.|  
|[get\_ForeColor](../Topic/CStockPropImpl::get_ForeColor.md)|Appelez cette méthode pour obtenir la couleur de premier plan du contrôle.|  
|[get\_HWND](../Topic/CStockPropImpl::get_HWND.md)|Appelez cette méthode pour obtenir le handle de fenêtre associée au contrôle.|  
|[get\_MouseIcon](../Topic/CStockPropImpl::get_MouseIcon.md)|Appelez cette méthode pour obtenir les propriétés d'image du graphique \(icônes, bitmaps, ou métafichier\) à afficher lorsque la souris se trouve sur le contrôle.|  
|[get\_MousePointer](../Topic/CStockPropImpl::get_MousePointer.md)|Appelez cette méthode pour obtenir le type du pointeur de la souris affiche lorsque la souris se trouve sur le contrôle, par exemple, de flèche, de mélange, ou sablier de.|  
|[get\_Picture](../Topic/CStockPropImpl::get_Picture.md)|Appelez cette méthode pour obtenir un pointeur vers les propriétés d'image d'un graphique \(icônes, bitmaps, ou métafichier\) soit affiché.|  
|[get\_ReadyState](../Topic/CStockPropImpl::get_ReadyState.md)|Appelez cette méthode pour accéder à l'état prêt du contrôle, par exemple, charger ou est chargé.|  
|[get\_TabStop](../Topic/CStockPropImpl::get_TabStop.md)|Appelez cette méthode pour obtenir la balise qui indique si le contrôle est un taquet de tabulation ou pas.|  
|[get\_Text](../Topic/CStockPropImpl::get_Text.md)|Appelez cette méthode pour obtenir le texte restitué avec le contrôle.|  
|[get\_Valid](../Topic/CStockPropImpl::get_Valid.md)|Appelez cette méthode pour obtenir l'état de la balise qui indique si le contrôle est valide ou pas.|  
|[get\_Window](../Topic/CStockPropImpl::get_Window.md)|Appelez cette méthode pour obtenir le handle de fenêtre associée au contrôle.  Identique à [CStockPropImpl::get\_HWND](../Topic/CStockPropImpl::get_HWND.md).|  
|[put\_Appearance](../Topic/CStockPropImpl::put_Appearance.md)|Appelez cette méthode pour définir le style de peinture utilisé par le contrôle, par exemple, plate ou 3D.|  
|[put\_AutoSize](../Topic/CStockPropImpl::put_AutoSize.md)|Appelez cette méthode pour définir la valeur de la balise qui indique si le contrôle ne peut pas être aucune autre taille.|  
|[put\_BackColor](../Topic/CStockPropImpl::put_BackColor.md)|Appelez cette méthode pour définir la couleur d'arrière\-plan du contrôle.|  
|[put\_BackStyle](../Topic/CStockPropImpl::put_BackStyle.md)|Appelez cette méthode pour définir le style d'arrière\-plan du contrôle.|  
|[put\_BorderColor](../Topic/CStockPropImpl::put_BorderColor.md)|Appelez cette méthode pour définir la couleur de la bordure du contrôle.|  
|[put\_BorderStyle](../Topic/CStockPropImpl::put_BorderStyle.md)|Appelez cette méthode pour définir le style de bordure du contrôle.|  
|[put\_BorderVisible](../Topic/CStockPropImpl::put_BorderVisible.md)|Appelez cette méthode pour définir la valeur de la balise qui indique si la bordure du contrôle est visible ou non.|  
|[put\_BorderWidth](../Topic/CStockPropImpl::put_BorderWidth.md)|Appelez cette méthode pour définir la largeur de la bordure du contrôle.|  
|[put\_Caption](../Topic/CStockPropImpl::put_Caption.md)|Appelez cette méthode pour définir le texte à afficher avec le contrôle.|  
|[put\_DrawMode](../Topic/CStockPropImpl::put_DrawMode.md)|Appelez cette méthode pour définir le mode dessin du contrôle, par exemple, stylet de bits XOR ou pour inverser les couleurs.|  
|[put\_DrawStyle](../Topic/CStockPropImpl::put_DrawStyle.md)|Appelez cette méthode pour définir le style de dessin du contrôle, par exemple, unie, précipité, ou en pointillés.|  
|[put\_DrawWidth](../Topic/CStockPropImpl::put_DrawWidth.md)|Appelez cette méthode pour définir la largeur \(en pixels\) utilisée par les méthodes de dessin du contrôle.|  
|[put\_Enabled](../Topic/CStockPropImpl::put_Enabled.md)|Appelez cette méthode pour affecter à l'indicateur qui indique si le contrôle est activé.|  
|[put\_FillColor](../Topic/CStockPropImpl::put_FillColor.md)|Appelez cette méthode pour définir la couleur de remplissage du contrôle.|  
|[put\_FillStyle](../Topic/CStockPropImpl::put_FillStyle.md)|Appelez cette méthode pour définir le style du remplissage du contrôle, par exemple, unie, transparents, ou l'avez contre\-haché.|  
|[put\_Font](../Topic/CStockPropImpl::put_Font.md)|Appelez cette méthode pour définir les propriétés de police du contrôle.|  
|[put\_ForeColor](../Topic/CStockPropImpl::put_ForeColor.md)|Appelez cette méthode pour définir la couleur de premier plan du contrôle.|  
|[put\_HWND](../Topic/CStockPropImpl::put_HWND.md)|Cette méthode retourne E\_FAIL.|  
|[put\_MouseIcon](../Topic/CStockPropImpl::put_MouseIcon.md)|Appelez cette méthode pour définir les propriétés d'image du graphique \(icônes, bitmaps, ou métafichier\) à afficher lorsque la souris se trouve sur le contrôle.|  
|[put\_MousePointer](../Topic/CStockPropImpl::put_MousePointer.md)|Appelez cette méthode pour définir le type de pointeur de la souris affiche lorsque la souris se trouve sur le contrôle, par exemple, de flèche, de mélange, ou sablier de.|  
|[put\_Picture](../Topic/CStockPropImpl::put_Picture.md)|Appelez cette méthode pour définir les propriétés d'image d'un graphique \(icônes, bitmaps, ou métafichier\) à afficher.|  
|[put\_ReadyState](../Topic/CStockPropImpl::put_ReadyState.md)|Appelez cette méthode pour définir l'état prêt du contrôle, par exemple, charger ou est chargé.|  
|[put\_TabStop](../Topic/CStockPropImpl::put_TabStop.md)|Appelez cette méthode pour définir la valeur de la balise qui indique si le contrôle est un taquet de tabulation ou pas.|  
|[put\_Text](../Topic/CStockPropImpl::put_Text.md)|Appelez cette méthode pour définir le texte restitué avec le contrôle.|  
|[put\_Valid](../Topic/CStockPropImpl::put_Valid.md)|Appelez cette méthode pour affecter à l'indicateur qui indique si le contrôle est valide ou pas.|  
|[put\_Window](../Topic/CStockPropImpl::put_Window.md)|Cette méthode appelle [CStockPropImpl::put\_HWND](../Topic/CStockPropImpl::put_HWND.md), qui retourne E\_FAIL.|  
|[putref\_Font](../Topic/CStockPropImpl::putref_Font.md)|Appelez cette méthode pour définir les propriétés de police du contrôle, avec un décompte de références.|  
|[putref\_MouseIcon](../Topic/CStockPropImpl::putref_MouseIcon.md)|Appelez cette méthode pour définir les propriétés d'image du graphique \(icônes, bitmaps, ou métafichier\) à afficher lorsque la souris se trouve sur le contrôle, avec un décompte de références.|  
|[putref\_Picture](../Topic/CStockPropImpl::putref_Picture.md)|Appelez cette méthode pour définir les propriétés d'image d'un graphique \(icônes, bitmaps, ou métafichier\) à afficher, avec un décompte de références.|  
  
## Notes  
 `CStockPropImpl` fournit **put** et les méthodes de **get** pour chacune stockent la propriété.  Ces méthodes fournissent le code nécessaire pour définir ou pour obtenir les données membres associée à chaque propriété et l'annoncer et synchroniser avec le conteneur lorsqu'une propriété change.  
  
 Visual C\+\+ prend en charge des propriétés stock via ses assistants.  Pour plus d'informations sur l'ajout de propriétés stock à un contrôle, consultez [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md).  
  
 Pour la compatibilité descendante, `CStockPropImpl` expose également `get_Window` et les méthodes d' `put_Window` qui appelle simplement `get_HWND` et `put_HWND`, respectivement.  L'implémentation par défaut d' `put_HWND` retourne **E\_FAIL** comme `HWND` doit être une propriété en lecture seule.  
  
 Les propriétés suivantes ont également une implémentation de **putref** :  
  
-   Police  
  
-   MouseIcon  
  
-   Picture  
  
 Les mêmes trois propriétés stock requièrent leur donnée membre correspondante d'être de type `CComPtr` ou d'une autre classe qui fournit le décompte de références correct d'interface au moyen de l'opérateur d'assignation.  
  
## Hiérarchie d'héritage  
 `T`  
  
 [IDispatchImpl](../../atl/reference/idispatchimpl-class.md)  
  
 `CStockPropImpl`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)   
 [IDispatchImpl Class](../../atl/reference/idispatchimpl-class.md)
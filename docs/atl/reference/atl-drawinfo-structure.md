---
title: "ATL_DRAWINFO Structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::ATL_DRAWINFO"
  - "ATL_DRAWINFO"
  - "ATL.ATL_DRAWINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL_DRAWINFO structure"
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
caps.latest.revision: 16
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL_DRAWINFO Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Contient des informations utilisées pour afficher à différentes cibles, telles qu'une imprimante, un métafichier, ou un contrôle ActiveX.  
  
## Syntaxe  
  
```  
  
      struct ATL_DRAWINFO{  
   UINT cbSize;  
   DWORD dwDrawAspect;  
   LONG lindex;  
   DVTARGETDEVICE* ptd;  
   HDC hicTargetDev;  
   HDC hdcDraw;  
   LPCRECTL prcBounds;  
   LPCRECTL prcWBounds;  
   BOOL bOptimize;  
   BOOL bZoomed;  
   BOOL bRectInHimetric;  
   SIZEL ZoomNum;  
   SIZEL ZoomDen;  
};  
```  
  
## Membres  
 `cbSize`  
 La taille de la structure, en octets.  
  
 **dwDrawAspect**  
 Spécifie comment la cible doit être représentée.  Les représentations peuvent inclure le contenu, une icône, un aperçu, ou un document imprimé.  Pour obtenir la liste des valeurs possibles, consultez [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) et le [DVASPECT2](http://msdn.microsoft.com/library/windows/desktop/ms688644).  
  
 **lindex**  
 Partie de la cible présentant un intérêt pour l'opération de dessin.  Sa traduction varie en fonction de la valeur dans le membre de **dwDrawAspect** .  
  
 **ptd**  
 Pointeur vers une structure de [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) qui active des optimisations de dessin selon l'aspect spécifié.  Notez que de nouveaux objets et conteneurs que les interfaces de dessin optimisées par prennent en charge ce membre.  Les objets et les conteneurs plus anciens qui ne prennent pas en charge les interfaces de dessin optimisées spécifient toujours **NULL** pour ce membre.  
  
 **hicTargetDev**  
 Le contexte d'informations pour l'appareil cible a globale pointe vers **ptd** à partir duquel l'objet peut récupérer la métrique du périphérique et teste les fonctionnalités de l'appareil.  Si **ptd** est **NULL**, l'objet doit ignorer la valeur du membre de **hicTargetDev** .  
  
 **hdcDraw**  
 Le contexte de périphérique sur lequel à dessiner.  Pour un objet sans fenêtre, le membre de **hdcDraw** est en mode de mappage d' `MM_TEXT` avec ses coordonnées logiques correspondant à des coordonnées clientes de la fenêtre contenante.  En outre, le contexte de périphérique doit se trouver dans le même état comme celle normalement passé par un message d' `WM_PAINT` .  
  
 **prcBounds**  
 Pointeur vers une structure de [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907) spécifiant le rectangle sur **hdcDraw** et dans lequel l'objet doit être dessiné.  Ce membre contrôle positionner et étirer de l'objet.  Ce membre doit être **NULL** pour dessiner un objet actif sur place sans fenêtre.  Dans chaque autre situation, **NULL** n'est pas une valeur autorisée et doit entraîner un code d'erreur d' `E_INVALIDARG` .  Si le conteneur passe une valeur non de**NULL** à un objet sans fenêtre, l'objet doit afficher l'aspect demandé dans le contexte et le rectangle spécifié de périphérique.  Un conteneur peut demander cette opération d'un objet sans fenêtre pour afficher une deuxième, inactive vue de l'objet ou pour imprimer l'objet.  
  
 **prcWBounds**  
 Si **hdcDraw** est un contexte de périphérique de métafichier \(consultez [GetDeviceCaps](http://msdn.microsoft.com/library/windows/desktop/dd144877) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]\), c'est un pointeur vers une structure de **RECTL** spécifiant le rectangle englobant dans le métafichier sous\-jacent.  La structure de rectangle contient l'étendue de la fenêtre et l'origine de la fenêtre.  Ces valeurs sont utiles pour dessiner des métafichiers.  Le rectangle indiqué par **prcBounds** est imbriqué à l'intérieur de le rectangle de **prcWBounds** ; ils sont dans le même espace de coordonnées.  
  
 **bOptimize**  
 Une valeur différente de zéro si le dessin du contrôle doit être optimisé, sinon 0.  Si le dessin est optimisé, l'état du contexte de périphérique est automatiquement restauré lorsque vous avez terminé de rendu.  
  
 **bZoomed**  
 Une valeur différente de zéro si la cible est un facteur de zoom, sinon 0.  Le facteur de zoom est stocké dans **ZoomNum**.  
  
 **bRectInHimetric**  
 Une valeur différente de zéro si les dimensions de **prcBounds** sont dans **HIMETRIC**, sinon 0.  
  
 **ZoomNum**  
 La largeur et la hauteur du rectangle dans lequel l'objet est affiché.  Le facteur de zoom sur l'axe des abscisses \(la proportion de la taille naturelle de l'objet jusqu'à son degré actuel\) de la cible est la valeur de **ZoomNum.cx** s'est divisé par la valeur de **ZoomDen.cx**.  Le facteur de zoom sur l'axe Y est accompli de la même façon.  
  
 **ZoomDen**  
 La largeur et la hauteur réelle de la cible.  
  
## Notes  
 L'utilisation courante de cette structure est la recherche des informations pendant le rendu de l'objet cible.  Par exemple, vous pouvez récupérer des valeurs d' `ATL_DRAWINFO` à l'intérieur de la surcharge de [CComControlBase::OnDrawAdvanced](../Topic/CComControlBase::OnDrawAdvanced.md).  
  
 Cette structure stocke des informations pertinentes utilisées pour afficher l'apparence d'un objet pour l'appareil cible.  Les informations fournies peuvent être utilisées dans le dessin à l'écran, à une imprimante, ou même dans un métafichier.  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)   
 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)   
 [CComControlBase::OnDrawAdvanced](../Topic/CComControlBase::OnDrawAdvanced.md)
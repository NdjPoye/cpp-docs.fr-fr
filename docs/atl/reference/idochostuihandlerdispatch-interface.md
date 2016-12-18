---
title: "IDocHostUIHandlerDispatch Interface | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDocHostUIHandlerDispatch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDocHostUIHandlerDispatch interface"
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDocHostUIHandlerDispatch Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une interface à l'analyse et au moteur de rendu HTML Microsoft.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
interface IDocHostUIHandlerDispatch : IDispatch  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
> [!NOTE]
>  Les liens dans le tableau suivant sont des rubriques de référence d'INet Kit de développement logiciel pour les membres de l'interface d' [IDocUIHostHandler](https://msdn.microsoft.com/en-us/library/aa753260.aspx) .  `IDocHostUIHandlerDispatch` a les mêmes fonctionnalités que **IDocUIHostHandler**, à la différence étant cet `IDocHostUIHandlerDispatch` est une dispinterface pendant qu' **IDocUIHostHandler** est une interface personnalisée.  
  
|||  
|-|-|  
|[\<caps:sentence id\="tgt7" sentenceid\="bbafd0070a97938421603b1ef8409510" class\="tgtSentence"\>EnableModeless\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753253.aspx)|Appel de l'implémentation de MSHTML d' [IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115).  Également appelé lorsque MSHTML affiche l'interface utilisateur modal.|  
|[\<caps:sentence id\="tgt10" sentenceid\="2cfbfb70fe0af79263134b694d06311c" class\="tgtSentence"\>FilterDataObject\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753254.aspx)|A appelé sur l'hôte en MSHTML à permettre à l'hôte pour remplacer l'objet de données de MSHTML.|  
|[\<caps:sentence id\="tgt12" sentenceid\="715255e2d7f611c97308a373328e19a0" class\="tgtSentence"\>GetDropTarget\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753255.aspx)|Appelé par MSHTML lorsqu'il est utilisé comme cible de déplacement pour permettre à l'hôte de fournir autre [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679).|  
|[\<caps:sentence id\="tgt14" sentenceid\="5a51a8633a0d2036f843073d6f35a4af" class\="tgtSentence"\>GetExternal\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753256.aspx)|Appelé par MSHTML pour obtenir l'interface de IDispatch de l'hôte.|  
|[\<caps:sentence id\="tgt16" sentenceid\="ce27e0c2f7ebb0aaa2f9088818dc8347" class\="tgtSentence"\>GetHostInfo\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753257.aspx)|Récupère les fonctions d'interface utilisateur de l'hôte de MSHTML.|  
|[\<caps:sentence id\="tgt18" sentenceid\="693bd2149b17c4586cdc167e13e59f0a" class\="tgtSentence"\>GetOptionKeyPath\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753258.aspx)|Retourne la clé de Registre sous laquelle MSHTML stocke les préférences de l'utilisateur.|  
|[\<caps:sentence id\="tgt20" sentenceid\="7fce94585b477684cc21a38fe9ee288c" class\="tgtSentence"\>HideUI\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753259.aspx)|Appelé lorsque MSHTML supprime ses menus et barres d'outils.|  
|[\<caps:sentence id\="tgt22" sentenceid\="359e4dcbd80b962decf88ef02d66fe14" class\="tgtSentence"\>OnDocWindowActivate\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753261.aspx)|Appel de l'implémentation de MSHTML d' [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281).|  
|[\<caps:sentence id\="tgt24" sentenceid\="8e472d7f3f3064d2ee6fdddd83002b86" class\="tgtSentence"\>OnFrameWindowActivate\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753262.aspx)|Appel de l'implémentation de MSHTML d' [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969).|  
|[\<caps:sentence id\="tgt26" sentenceid\="3fd38deec5e9f4201074e886bfb178a5" class\="tgtSentence"\>ResizeBorder\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753263.aspx)|Appel de l'implémentation de MSHTML d' [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053).|  
|[\<caps:sentence id\="tgt28" sentenceid\="2f382ba3de5494d18b20ccfa348f795e" class\="tgtSentence"\>ShowContextMenu\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753264.aspx)|Appelé de MSHTML pour afficher un menu contextuel.|  
|[\<caps:sentence id\="tgt30" sentenceid\="c6978c4c8ab30ae8380439da613bb63c" class\="tgtSentence"\>ShowUI\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753265.aspx)|Permet à l'hôte pour remplacer les menus et les barres d'outils de MSHTML.|  
|[\<caps:sentence id\="tgt32" sentenceid\="97bfd5aead25a2d9870b38da4b6745cd" class\="tgtSentence"\>TranslateAccelerator\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753266.aspx)|Appelé par MSHTML lorsque [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) ou [IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756) est appelé.|  
|[\<caps:sentence id\="tgt34" sentenceid\="55c20a6fb6b05f6059d72b2854a7d7e2" class\="tgtSentence"\>TranslateUrl\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753267.aspx)|Appelé par MSHTML pour permettre à l'hôte la possibilité de modifier l'URL à charger.|  
|[\<caps:sentence id\="tgt36" sentenceid\="8fdf7c2c3ebf5fa12ecc909279c951ff" class\="tgtSentence"\>UpdateUI\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/aa753268.aspx)|Avertit l'hôte que l'état de commande a changé.|  
  
## Notes  
 Un hôte peut substituer les menus, les barres d'outils, et les menus contextuels utilisés par l'analyse du code HTML de Microsoft et le convertisseur \(MSHTML\) lorsque vous implémentez cette interface.  
  
## Configuration requise  
 La définition de cette interface est disponible en tant que fichier IDL ou C\+\+, comme indiqué ci\-dessous.  
  
|Type de définition|Fichier|  
|------------------------|-------------|  
|IDL|ATLIFace.idl|  
|C\+\+|ATLIFace.h \(également inclus dans ATLBase.h\)|  
  
## Voir aussi  
 [IDocUIHostHandler](https://msdn.microsoft.com/en-us/library/aa753260.aspx)
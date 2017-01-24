---
title: "TN040&#160;: redimensionnement et zoom sur place MFC/OLE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "activation sur place, zoomer et redimensionner"
  - "redimensionner sur place"
  - "TN040"
  - "zoom et activation sur place"
ms.assetid: 4d7859bd-0b2e-4254-be62-2735cecf02c6
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN040&#160;: redimensionnement et zoom sur place MFC/OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Cette remarque discutera les problèmes concernant la modification en place et comment un serveur doit accomplir un zoom correct et un redimensionnement en place.  Avec l'activation en place, le concept de WYSIWYG est pris un peu plus loin dans la mesure où les conteneurs et les serveurs coopèrent entre eux, et interprètent en particulier la spécification OLE à peu près de la même manière.  
  
 En raison de l'interaction proche entre un conteneur et un serveur prenant en charge l'activation en place, il existe un certain nombre d'attentes de l'utilisateur qui doivent être conservées :  
  
-   L'affichage de présentation \(un métafichier dessiné dans la substitution de `COleServerItem::OnDraw` \) doit apparaître exactement le même que s'il est dessiné pour la retouche \(sauf que les outils de retouche ne sont pas visible\).  
  
-   Lorsque le conteneur zoome, la fenêtre de serveur doit aussi \!  
  
-   Le conteneur et le serveur doivent afficher des objets de modification utilisant les mêmes mesures.  Cela signifie l'utilisation d'un mode de mappage en fonction du nombre de pixels par pouce *logiques* — pixels par pouce non physiques, lors du rendu sur le périphérique d'affichage.  
  
> [!NOTE]
>  Étant donné que l'activation en place s'applique uniquement aux éléments qui sont incorporés \(non liés\), le zoom s'applique uniquement aux objets incorporés.  Vous verrez des API utilisés pour zoomer dans `COleServerDoc` et `COleServerItem`.  La raison de cette dichotomie est que seules les fonctions qui ne sont pas valides pour les éléments liés et incorporés sont dans `COleServerItem` \(cela vous permet d'avoir une implémentation commune\) et les fonctions qui sont valides uniquement pour les objets incorporés figurent dans la classe `COleServerDoc` \(du point de vue du serveur, c'est `document` qui est incorporé\).  
  
 La majorité de la charge est placée sur l'implémenteur du serveur, car le serveur doit avoir connaissance du facteur de zoom du conteneur et modifier son interface de modification comme il convient.  Mais comment le serveur détermine\-il le facteur de zoom utilisé par le conteneur ?  
  
## Prise en charge du zoom par MFC  
 Le facteur de zoom actuel peut être déterminé en appelant `COleServerDoc::GetZoomFactor`.  Appeler cette fonction lorsque le document n'est pas actif en place aura toujours pour résultat un facteur de zoom 100% \(ou un rapport de 1:1\).  L'appeler en étant actif en place peut retourner quelque chose d'autre que 100%.  
  
 Pour un exemple de zoom correct, consultez l'exemple MFC OLE [HIERSVR](../top/visual-cpp-samples.md).  Le zoom dans HIERSVR est compliqué par le fait qu'il affiche le texte, et le texte, en général, n'évolue pas de façon linéaire \(indicateurs, conventions typographiques, largeurs de création, et hauteurs compliquent le problème\).  Toutefois, HIERSVR est une référence sensée pour implémenter le zoom correctement, tout comme le tutoriel MFC [SCRIBBLE](../top/visual-cpp-samples.md) \(étape 7\).  
  
 `COleServerDoc::GetZoomFactor` détermine le facteur de zoom d'après plusieurs mesures disponibles dans le conteneur ou dans l'implémentation de vos classes `COleServerItem` et `COleServerDoc`.  En bref, le facteur de zoom courant est déterminé par la formule suivante :  
  
```  
Position Rectangle (PR) / Container Extent (CE)  
```  
  
 Le RECTANGLE de POSITION est déterminé par le conteneur.  Il est retourné au serveur lors de l'activation en place lorsque `COleClientItem::OnGetItemPosition` est appelée et est mis à jour lorsque le conteneur appelle `COleServerDoc::OnSetItemRects` du serveur \(avec un appel à `COleClientItem::SetItemRects`\).  
  
 L'étendue du conteneur est légèrement plus complexe à calculer.  Si le conteneur a appelé `COleServerItem::OnSetExtent` \(par un appel à `COleClientItem::SetExtent`\), l'étendue de conteneur est cette valeur est convertie en pixels basé sur le nombre de pixels par pouce logique.  Si le conteneur n'a pas appelé SetExtent \(ce qui est généralement le cas\), l'étendue de conteneur est la taille retournée par `COleServerItem::OnGetExtent`.  Par conséquent, si le conteneur n'a pas appelé SetExtent, l'infrastructure suppose que si c'était le cas, le conteneur l'aurait appelé avec 100% de l'extension naturelle \(valeur retournée par **COleServerItem::GetExtent**\).  Dit d'une autre manière, l'infrastructure suppose que le conteneur affiche 100% \(ni plus, ni moins\) de l'élément.  
  
 Il est important de noter que même si `COleServerItem::OnSetExtent` et `COleServerItem::OnGetExtent` ont des noms semblables, ils ne manipulent pas le même attribut de l'élément.  `OnSetExtent` est appelé pour indiquer au serveur quelle quantité de l'objet est visible dans le conteneur \(quel que soit le facteur de zoom\) et `OnGetExtent` est appelé par le conteneur afin de déterminer la taille idéale de l'objet.  
  
 En consultant chacun des API en jeu, vous pouvez obtenir une image plus claire :  
  
## COleServerItem::OnGetExtent  
 Cette fonction doit retourner la « taille d'origine » en unités HIMETRIC de l'élément.  Le meilleur moyen de visualiser la « taille d'origine » consiste à la définir comme la taille à laquelle il peut apparaître une fois imprimée.  La valeur retournée est ici constante pour le contenu d'un élément donné \(comme un métafichier, qui est constant pour un élément particulier\).  Cette valeur ne change pas lorsque le zoom est appliqué à l'élément.  Elle ne change généralement pas lorsque le conteneur donne à l'élément plus ou moins d'espace en appelant `OnSetExtent`.  Un exemple d'une modification peut être celui d'un simple éditeur de texte sans fonction de "marge" qui a inclus le texte en fonction de la dernière extension envoyée par le conteneur.  Si un serveur est modifié, le serveur doit probablement définir le bit OLEMISC\_RECOMPOSEONRESIZE dans le registre système \(consultez la documentation OLESDK pour plus d'informations sur cette option\).  
  
## COleServerItem::OnSetExtent  
 Cette fonction est appelée lorsque le conteneur montre "plus ou moins" de l'objet.  La plupart des conteneurs n'appelleront pas cela du tout.  L'implémentation par défaut fournit la dernière valeur acceptée du conteneur dans « m\_sizeExtent », qui est utilisé dans `COleServerDoc::GetZoomFactor` lors du calcul de la valeur d'étente du conteneur décrite ci\-dessus.  
  
## COleServerDoc::OnSetItemRects  
 Cette fonction est appelée uniquement lorsque le document est actif en place.  Elle est appelée lorsque le conteneur met à jour soit la position soit la réduction appliquée à l'élément.  Le RECTANGLE de POSITION, comme discuté ci\-dessus, fournit le numérateur du calcul du facteur de zoom.  Un serveur peut demander que la position de l'élément soit modifiée en appelant `COleServerDoc::RequestPositionChange`.  Le conteneur peut ne pas répondre à la demande en appelant `OnSetItemRects` \(par un appel à **COleServerItem::SetItemRects**\).  
  
## COleServerDoc::OnDraw  
 Il est important de savoir que le métafichier créé en entrant `COleServerItem::OnDraw` produit exactement le même métafichier, quel que soit le facteur de zoom actuel.  Le conteneur mettra à l'échelle le métafichier comme il convient.  Il s'agit d'une distinction importante entre `OnDraw` de la vue et `OnDraw`de l'élément du serveur.  La vue gère le zoom, l'élément crée simplement un métafichier *zoomable* et laisse le conteneur faire le zoom approprié.  
  
 Le meilleur moyen d'assurer que le serveur fonctionne correctement consiste à utiliser l'implémentation `COleServerDoc::GetZoomFactor` si votre document est actif en place.  
  
## Prise en charge MFC pour le redimensionnement en place  
 MFC implémente entièrement l'interface de redimensionnement en place comme décrit dans la spécification OLE 2.  L'interface utilisateur est prise en charge par la classe `COleResizeBar`, un message **WM\_SIZECHILD**personnalisé, et un traitement spécial de ce message dans `COleIPFrameWnd`.  
  
 Vous pouvez vouloir implémenter une gestion différente de ce message que celle fournie par l'infrastructure.  Comme décrit ci\-dessus, l'infrastructure conserve les résultats de redimensionnement en place jusqu'à un conteneur — le serveur répond au changement du facteur de zoom.  Si le conteneur réagit en définissant l'étendue de conteneur et le RECTANGLE de POSITION lors du traitement de son `COleClientItem::OnChangeItemPosition` \(appelé à la suite d'un appel à `COleServerDoc::RequestPositionChange`\) alors le rendimensionnement en place donnera un élément apparaissant « pratiquement » dans la fenêtre de modification.  Si le conteneur réagit en définissant uniquement le RECTANGLE de POSITION pendant le traitement de `COleClientItem::OnChangeItemPosition`, le facteur de zoom change et l'élément est lu « zoomé ».  
  
 Un serveur peut contrôler \(à un certain degré\) ce qui se produit lors de la négociation.  Une feuille de calcul, par exemple peut choisir d'afficher plus ou moins de cellules lorsque l'utilisateur redimensionne la fenêtre en modifiant l'élément en place.  Un traitement de texte peut choisir de modifier les "marges" de page pour qu'elles soient identiques à la fenêtre et ré\-inclure le texte dans les nouvelles marges.  Les serveurs implémentent ce problème en modifiant l'extension naturelle \(la valeur retournée par `COleServerItem::OnGetExtent`\) lorsque le redimensionnement est effectué.  Cela entraînera la modification du RECTANGLE de POSITION et de l'étendue de conteneur par le même volume, ce qui donne le même facteur de zoom, mais une plus grande ou plus petite zone d'affichage.  En outre, la plupart du document est visible dans un métafichier généré par `OnDraw`.  Dans ce cas, le document lui\-même change lorsque l'utilisateur redimensionne l'élément, et non seulement la zone d'affichage.  
  
 Vous pouvez implémenter un redimensionnement personnalisé tout en tirant parti de l'interface utilisateur fournie par `COleResizeBar` en remplaçant le message **WM\_SIZECHILD** dans votre classe `COleIPFrameWnd`.  Pour plus d'informations sur les détails de **WM\_SIZECHILD**, consultez la [Note technique 24](../mfc/tn024-mfc-defined-messages-and-resources.md).  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)
---
title: "Documents actifs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "documents actifs (C++)"
  - "documents actifs (C++), spécification"
  - "documents actifs (C++), vues"
  - "OLE (C++), documents actifs"
  - "objets de vue, spécification"
  - "vues (C++), documents actifs"
ms.assetid: 1378f18e-aaa6-420b-8501-4b974905baa0
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Documents actifs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les documents actifs étendent la technologie de document composite OLE.  Ces extensions sont fournies sous la forme d'autres interfaces qui gèrent les vues, afin que des objets puissent s'exécuter dans des conteneurs tout en conservant le contrôle de l'affichage et des fonctions d'impression.  Ce processus permet d'afficher des documents dans des cadres sur le \(tels que Classeur Microsoft Office ou Microsoft Internet Explorer\) et dans les cadres natifs \(tels que les propres ports de la vue du produit\).  
  
 Cette section décrit [conditions requises pour les documents actifs](#requirements_for_active_documents) d'un point de vue fonctionnel.  Le document actif possède un jeu de données et a accès au stockage dans lequel les données peuvent être enregistrées et récupérées.  Il peut créer et gérer une ou plusieurs vues sur ses données.  En plus de prendre en charge l'incorporation et les interfaces classiques d'activation sur place des documents OLE, le document actif communique sa capacité à créer des vues via `IOleDocument`.  Dans cette interface, le conteneur peut demander à créer \(et énumérer\) les vues que dans le document actif peut afficher.  Dans cette interface, le document actif peut également fournir des informations diverses sur lui\-même, par exemple s'il prend en charge plusieurs vues ou rectangles complexes.  
  
 Voici l'interface **IOleDocument** .  Notez que l'interface **IEnumOleDocumentViews** est un énumérateur OLE standard pour les types **IOleDocumentView \***.  
  
 `interface IOleDocument : IUnknown`  
  
 `{`  
  
 `HRESULT CreateView(`  
  
 `[in] IOleInPlaceSite *pIPSite,`  
  
 `[in] IStream *pstm,`  
  
 `[in] DWORD dwReserved,`  
  
 `[out] IOleDocumentView **ppView);`  
  
 `HRESULT GetDocMiscStatus([out] DWORD *pdwStatus);`  
  
 `HRESULT EnumViews(`  
  
 `[out] IEnumOleDocumentViews **ppEnum,`  
  
 `[out] IOleDocumentView **ppView);`  
  
 `}`  
  
 Chaque document actif doit avoir un fournisseur de cadre de vue avec cette interface.  Si le document n'est pas incorporé dans un conteneur, le serveur de document actif lui\-même doit fournir le cadre de la vue.  Toutefois, lorsque le document actif est incorporé dans un conteneur de documents actifs, le conteneur fournit le cadre de la vue.  
  
 Un document actif peut créer un ou plusieurs types de [vues](#requirements_for_view_objects) de ses données \(par exemple, standard, plan, mise en page, etc.\).  Les vues agissent comme des filtres dans lesquels les données peuvent être affichées.  Même si le document a qu'un seul type de vue, il est possible que vous vouliez encore prendre en charge plusieurs vues comme moyen de prendre en charge une fonctionnalité de nouvelle fenêtre \(par exemple, l'élément de **Nouvelle fenêtre** dans le menu **Fenêtre** dans les applications Office\).  
  
##  <a name="requirements_for_active_documents"></a> Conditions requises pour les documents actifs  
 Un document actif qui peut être affiché dans un conteneur de documents actifs doit :  
  
-   Utilisez les fichiers composites OLE comme mécanisme de stockage en implémentant `IPersistStorage`.  
  
-   Prend en charge les fonctionnalités de base d'incorporation de OLE documents, y compris **Create From File**.  Cela rend nécessaire les interfaces `IPersistFile`, `IOleObject`, et `IDataObject`.  
  
-   Prend en charge une ou plusieurs vues, chacune capable de l'activation sur place.  Autrement dit, les vues doivent prendre en charge l'interface `IOleDocumentView` ainsi que les interfaces `IOleInPlaceObject` et `IOleInPlaceActiveObject` \(utilisant l'interface  **IOleInPlaceSite** et **IOleInPlaceFrame** du conteneur\).  
  
-   Prend en charge les interfaces de document actif standard `IOleDocument`, `IOleCommandTarget`, et `IPrint`.  
  
 La connaissance de quand et comment utiliser les interfaces de côté deconteneur est impliqué dans ces conditions requises.  
  
##  <a name="requirements_for_view_objects"></a> Conditions requises pour les objets de vue  
 Un document actif peut créer une ou plusieurs vues de ses données.  Fonctionnellement, ces vues sont comme les ports sur une méthode particulière pour afficher les données.  Si un document actif ne prend en charge qu'une vue, le document actif et cette vue peuvent être implémentés en utilisant une seule classe.  **IOleDocument::CreateView** renvoie le pointeur d'interface `IOleDocumentView` du même objet.  
  
 Pour être représenté dans un conteneur de documents actifs, un composant de vue doit prendre en charge **IOleInPlaceObject** et **IOleInPlaceActiveObject** en plus de `IOleDocumentView`:  
  
 `interface IOleDocumentView : IUnknown`  
  
 `{`  
  
 `HRESULT SetInPlaceSite([in] IOleInPlaceSite *pIPSite);`  
  
 `HRESULT GetInPlaceSite([out] IOleInPlaceSite **ppIPSite);`  
  
 `HRESULT GetDocument([out] IUnknown **ppunk);`  
  
 `[input_sync] HRESULT SetRect([in] LPRECT prcView);`  
  
 `HRESULT GetRect([in] LPRECT prcView);`  
  
 `[input_sync] HRESULT SetRectComplex(`  
  
 `[in] LPRECT prcView,`  
  
 `[in] LPRECT prcHScroll,`  
  
 `[in] LPRECT prcVScroll,`  
  
 `[in] LPRECT prcSizeBox);`  
  
 `HRESULT Show([in] BOOL fShow);`  
  
 `HRESULT UIActivate([in] BOOL fUIActivate);`  
  
 `HRESULT Open(void);`  
  
 `HRESULT CloseView([in] DWORD dwReserved);`  
  
 `HRESULT SaveViewState([in] IStream *pstm);`  
  
 `HRESULT ApplyViewState([in] IStream *pstm);`  
  
 `HRESULT Clone(`  
  
 `[in] IOleInPlaceSite *pIPSiteNew,`  
  
 `[out] IOleDocumentView **ppViewNew);`  
  
 `}`  
  
 Chaque vue a un site de vue associé, qui encapsule le cadre de la vue et le port de vue \(HWND et une zone rectangulaire dans cette fenêtre\).  Le site expose cette fonctionnalité dans l'interface standard **IOleInPlaceSite** .  Notez qu'il est possible d'avoir plusieurs port d'affichage sur un seul HWND.  
  
 En général, chaque type de vue a une représentation affichée différente.  Par conséquent les vues et les sites de correspondance de vue doivent implémenter les interfaces d'impression si `IPrint` et `IContinueCallback`, respectivement.  Le cadre de la vue doit être en pourparlers avec le fournisseur d'affichage par **IPrint**  lors du démarrage de l'impression, afin que les en\-têtes, les pieds de page, les marges, et les éléments associés soient imprimés correctement.  Le fournisseur d'affichage notifie le cadre d'événements liés à l'impression via `IContinueCallback`.  Pour plus d'informations sur ces interfaces, consultez [Impression par programmation](../mfc/programmatic-printing.md).  
  
 Notez que si un document actif ne prend en charge qu'une vue, le document actif et cette vue peuvent être implémentés en utilisant une seule classe contrète.  **IOleDocument::CreateView** renvoie simplement le pointeur d'interface `IOleDocumentView` du même objet.  En bref, il n'est pas nécessaire qu'il existe deux instances de l'objet distinctes lorsqu'une seule vue est requise.  
  
 Un objet de vue peut également être une cible de commande.  En implémentant `IOleCommandTarget` une vue peut accepter les commandes qui proviennent de l'interface utilisateur du conteneur \(notamment **Nouveau**, **Ouvrir**, **Enregistrer sous**, **Print** dans le menu de **Fichier** ; et **Copier**, **Coller**, **Annuler** dans le menu de **Modifier** \).  Pour plus d'informations, consultez [Gestion des messages et cibles des commandes](../mfc/message-handling-and-command-targets.md).  
  
## Voir aussi  
 [Relation contenant\-contenu de document actif](../mfc/active-document-containment.md)
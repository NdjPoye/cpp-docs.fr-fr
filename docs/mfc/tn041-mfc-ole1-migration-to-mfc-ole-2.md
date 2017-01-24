---
title: "TN041&#160;: migration de MFC/OLE1 vers MFC/OLE 2 | Microsoft Docs"
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
  - "convertir OLE1 en OLE2"
  - "migrer OLE1 vers OLE2"
  - "migration (C++), OLE1 vers OLE2"
  - "OLE1 (C++)"
  - "OLE2 (C++)"
  - "porter OLE1 vers OLE2"
  - "TN041"
  - "mettre à niveau les applications Visual C++, OLE1 vers OLE2"
ms.assetid: 67f55552-4b04-4ddf-af0b-4d9eaf5da957
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN041&#160;: migration de MFC/OLE1 vers MFC/OLE 2
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
## Problèmes généraux relatifs à la migration  
 Un des objectifs pour les classes OLE 2 de MFC \(2,5 et ultérieur\) est de maintenir un bon nombre des mêmes architectures insérées dans MFC 2,0 pour la prise en charge OLE 1,0.  Par conséquent, de nombreuses OLE classes de MFC 2,0 existent toujours dans cette version de MFC \(`COleDocument`, `COleServerDoc`, `COleClientItem`, `COleServerItem`\).  En outre, la plupart des API de ces classes sont identiques.  Toutefois, OLE 2 est rigoureusement différent de OLE 1,0 comme vous pouvez constater que certains détails ont changé.  Si vous connaissez la prise en charge de MFC 2.0 " s OLE1, vous serez à l'aise avec prise en charge de MFC 2,0.  
  
 Si vous effectuez une application MFC\/OLE1 existante et lui ajoutez la fonctionnalité OLE 2, vous devez lire cette remarque en premier.  Cette remarque aborde des problèmes généraux que vous pouvez rencontrer lors du déplacement de la fonctionnalité OLE1 de MFC\/OLE 2 et présente les problèmes découverts lors de le déplacement de deux applications incluses dans MFC 2,0 : les exemples de liaison et incorporation d'objets MFC [OCLIENT](../top/visual-cpp-samples.md) et [HIERSVR](../top/visual-cpp-samples.md).  
  
## L'architecture documents\/Vue de MFC est importante  
 Si votre application n'utilise pas l'architecture documents\/Vue de MFC et que vous voulez ajouter une prise en charge OLE 2 vers votre application, est maintenant l'heure pour passer au document\/vue.  Nombreux avantages OLE de MFC 2 classes sont réalisés uniquement une fois que votre application utilise l'architecture et composants intégrés de MFC.  
  
 Implémenter un serveur ou un conteneur sans utiliser l'architecture de MFC est possible, mais non conseillé.  
  
## Implémentation MFC à la place de vos propres  
 MFC « implémentation de la classe » `CToolBar`par exemple, `CStatusBar`, et ont `CScrollView` code intégré de cas pour la prise en charge OLE 2.  Par conséquent, si vous pouvez utiliser ces classes dans votre application vous bénéficierez des efforts mis en œuvre pour vous familiariser avec leur OLE.  De nouveau, il est possible de « lancer\-vos\-propres » classes ici pour ces objectifs, mais ce n'est pas suggéré.  Si vous devez implémenter des fonctionnalités similaires, le code source de MFC est une excellente référence pour traiter certains points plus fins OLE \(notamment quand il s'agit d'activation sur place\).  
  
## Vérifiez le code de l'exemple MFC  
 Il existe un certain nombre de MFC incluant la fonctionnalité OLE.  Chacune de ces applications implémente OLE d'un angle différent :  
  
-   [HIERSVR](../top/visual-cpp-samples.md) sert principalement pour une utilisation en tant qu'application serveur.  Elle est incluse dans MFC 2,0 comme une application MFC\/OLE1 et a été déplacée vers MFC\/OLE 2 et a l'étendue de sorte qu'il implémente de nombreuses OLE fonctionnalités disponibles dans OLE 2.  
  
-   [OCLIENT](../top/visual-cpp-samples.md) ceci est une application autonome conteneur, destinée à illustrer plusieurs OLE fonctionnalités d'un point de conteneur.  Il en a été déplacé de MFC 2,0, et est ensuite étendu pour prendre en charge plusieurs OLE fonctionnalités avancées, telles que les formats du presse\-papiers personnalisé et des liens vers des éléments imbriqués.  
  
-   [DRAWCLI](../top/visual-cpp-samples.md) cette application implémente la prise en charge du conteneur OLE comme OCLIENT fait, sauf qu'il fait dans le cadre d'un programme de dessin orienté objet existant.  Indique comment vous pouvez implémenter la prise en charge du conteneur OLE et l'intégrer dans votre application existante.  
  
-   [SUPERPAD](../top/visual-cpp-samples.md) cette application, ainsi qu'à une application autonome fine, est également un serveur OLE.  La prise en charge de serveur qu'il implémente est assez minimaliste.  Un intérêt particulier est la façon dont il utilise les services du presse\-papiers OLE pour copier des données vers le presse\-papiers, mais utilise la fonctionnalité intégrée au contrôle « remplacez » windows pour implémenter les fonctionnalités de coller à partir de le presse\-papiers.  Cela indique une combinaison intéressant d'utilisation et d'intégration traditionnelles d'API Windows avec les nouvelles API OLE.  
  
 Pour plus d'informations sur les exemples d'applications, consultez « utilisation d'exemple MFC ».  
  
## Étude de cas : OCLIENT de MFC 2,0  
 Comme discuté ci\-dessus, [OCLIENT](../top/visual-cpp-samples.md) a été inclus dans MFC 2,0 et implémenté avec OLE MFC\/OLE1.  Les étapes par lesquelles cette application a été initialement convertie pour utiliser MFC\/OLE 2 classes sont décrites ci\-dessous.  Plusieurs fonctions ont été ajoutées uniquement après que le port initial a été réglé pour illustrer le mieux les classes de MFC\/OLE.  Ces fonctionnalités ne sont pas couvertes ici ; reportez\-vous à l'exemple lui\-même pour plus d'informations sur les fonctionnalités avancées.  
  
> [!NOTE]
>  L'opération des erreurs de compilation étape par étape a été créée avec Visual C\+\+ 2.0.  Les messages d'erreur et les emplacements peuvent avoir changé avec Visual C\+\+ 4,0, mais les informations conceptuelles restent valides.  
  
## Les obtention de service  
 L'approche adoptée pour déplacer l'exemple de OCLIENT de MFC\/OLE est de commencer par le générer et résoudre des erreurs de compilateur évidentes qui résulteront.  Si vous prenez l'exemple d'OCLIENT à partir de MFC 2,0 et le compilez avec cette version de MFC, vous constaterez qu'il n'y a pas de nombreuses erreurs à résoudre.  Les erreurs dans l'ordre dans lequel elles se sont produites sont décrites ci\-dessous.  
  
## Compile et répare les erreurs  
  
```  
\oclient\mainview.cpp(104) : error C2660: 'Draw' : function does not take 4 parameters  
```  
  
 La première erreur affecte `COleClientItem::Draw`.  Dans MFC\/OLE1 cela a mis plus de paramètres que ce que la version de MFC\/OLE ne peut supporter.  Les paramètres supplémentaires n'étaient pas souvent nécessairement et généralement NULL \(comme dans cet exemple\).  Cette version de MFC peut déterminer automatiquement les valeurs des lpWBounds lorsque la capture de données en cours d'écriture est un contexte de périphérique de métafichier.  De plus, le paramètre de pFormatDC n'est plus nécessaire car l'infrastructure génère un attribut « contrôleur de domaine » du pDC transmis.  Pour résoudre ce problème, supprimez simplement les deux paramètres Null supplémentaires à l'appel de Dessiner.  
  
```  
\oclient\mainview.cpp(273) : error C2065: 'OLE_MAXNAMESIZE' : undeclared identifier  
\oclient\mainview.cpp(273) : error C2057: expected constant expression  
\oclient\mainview.cpp(280) : error C2664: 'CreateLinkFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
\oclient\mainview.cpp(286) : error C2664: 'CreateFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
\oclient\mainview.cpp(288) : error C2664: 'CreateStaticFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
```  
  
 Les erreurs ci\-dessus résultent du fait que tous les **COleClientItem::CreateXXXX** s'exécutent dans MFC\/OLE1 requis qu'un nom unique est passé pour représenter l'élément.  C'est une spécification de l'API OLE sous\-jacente.  Cela n'est pas nécessaire de MFC\/OLE 2 comme OLE 2 n'utilise pas DDE comme mécanisme sous\-jacent de communication \(le nom a été utilisé dans les appels DDE\).  Pour résoudre ce problème, vous pouvez supprimer la fonction de **CreateNewName** ainsi que toutes les références à cet élément.  Il est facile de déterminer ce que chaque fonction de MFC\/OLE attend dans cette version simplement en plaçant le curseur dans l'appel et en appuyant sur F1.  
  
 Une autre zone qui est très différente est gestion du presse\-papiers OLE 2.  Avec OLE1, vous avez utilisé le presse\-papiers Windows avec lequel les API du presse\-papiers interagissent.  Avec OLE 2 ceci est fait avec un autre mécanisme.  Les API MFC\/OLE1 supposent que le presse\-papiers a été ouvert avant la copie d'un objet `COleClientItem` dans le presse\-papiers.  Il n'est plus nécessaire et provoque toutes les opérations de le presse\-papiers de MFC\/OLE à l'échec.  Lorsque vous modifiez le code pour supprimer les dépendances sur **CreateNewName**, vous devez également supprimer le code qui ouvre et ferme le presse\-papiers windows.  
  
```  
\oclient\mainview.cpp(332) : error C2065: 'AfxOleInsertDialog' : undeclared identifier  
\oclient\mainview.cpp(332) : error C2064: term does not evaluate to a function  
\oclient\mainview.cpp(344) : error C2057: expected constant expression  
\oclient\mainview.cpp(347) : error C2039: 'CreateNewObject' : is not a member of 'CRectItem'  
```  
  
 Les erreurs résultent du gestionnaire de **CMainView::OnInsertObject**.  Gérer la commande de nouvel objet « insert » est une zone où les événements ont modifié un bit assez.  Dans ce cas, il est plus facile de fusionner simplement l'implémentation d'origine à celui fourni par AppWizard pour une application de conteneur OLE.  En fait, c'est une technique que vous pouvez appliquer au déplacement d'autres applications.  Dans MFC\/OLE1, vous pouvez afficher la boîte de dialogue « d'insertion » en appelant la fonction **AfxOleInsertDialog**.  Dans cette version vous construisez un objet du dialogue de **COleInsertObject** et appelez `DoModal`.  En outre, les nouveaux OLE éléments créés avec **CLSID** au lieu d'une chaîne de nom de la classe.  Le résultat final doit se présenter de la manière suivante :  
  
```  
COleInsertDialog dlg;  
if (dlg.DoModal() != IDOK)  
    return;  
  
BeginWaitCursor();  
  
CRectItem* pItem = NULL;  
TRY  
{  
    // First create the C++ object  
    pItem = GetDocument()->CreateItem();  
    ASSERT_VALID(pItem);  
  
    // Initialize the item from the dialog data.  
    if (!dlg.CreateItem(pItem))  
        AfxThrowMemoryException();  
           // any exception will do  
    ASSERT_VALID(pItem);  
  
    // run the object if appropriate  
    if (dlg.GetSelectionType() ==   
            COleInsertDialog::createNewItem)  
        pItem->DoVerb(OLEIVERB_SHOW, this);  
  
    // update right away  
    pItem->UpdateLink();  
    pItem->UpdateItemRectFromServer();  
  
    // set selection to newly inserted item  
    SetSelection(pItem);  
    pItem->Invalidate();  
}  
CATCH (CException, e)  
{    
    // clean up item  
    if (pItem != NULL)  
        GetDocument()->DeleteItem(pItem);  
  
    AfxMessageBox(IDP_FAILED_TO_CREATE);  
}  
END_CATCH  
  
EndWaitCursor();  
```  
  
> [!NOTE]
>  Nouvel objet d'insertion peut être différent pour votre application\) :  
  
 Il est également nécessaire de comprendre \<afxodlgs.h\> qui contient la déclaration de la classe de **COleInsertObject** ainsi que les autres boîtes de dialogue standard fournies par MFC.  
  
```  
\oclient\mainview.cpp(367) : error C2065: 'OLEVERB_PRIMARY' : undeclared identifier  
\oclient\mainview.cpp(367) : error C2660: 'DoVerb' : function does not take 1 parameters  
```  
  
 Ces erreurs sont causées par le fait que les constantes ont changé dans OLE 2, même si conceptuellement ce sont les mêmes.  Dans ce cas **OLEVERB\_PRIMARY** a changé à `OLEIVERB_PRIMARY`.  Dans OLE1 et OLE 2, le verbe principal est généralement exécuté par un conteneur lorsque l'utilisateur double\-cliquez sur un élément.  
  
 En outre, `DoVerb` prend maintenant un paramètre supplémentaire \(un pointeur vers une vue`CView`\(\*\).  Ce paramètre est uniquement utilisé pour implémenter la « modification sur place » \(ou l'activation sur place\).  Pour le moment vous affectez à ce paramètre NULL, car vous ne mettez pas cette fonctionnalité pour l'instant.  
  
 Pour être certain que l'infrastructure n'essaie jamais de s'activer dans l'emplacement, vous devez remplacer `COleClientItem::CanActivate` comme suit :  
  
```  
BOOL CRectItem::CanActivate()  
{  
    return FALSE;  
}  
  
\oclient\rectitem.cpp(53) : error C2065: 'GetBounds' : undeclared identifier  
\oclient\rectitem.cpp(53) : error C2064: term does not evaluate to a function  
\oclient\rectitem.cpp(84) : error C2065: 'SetBounds' : undeclared identifier  
\oclient\rectitem.cpp(84) : error C2064: term does not evaluate to a function  
```  
  
 Dans MFC\/OLE1, **COleClientItem::GetBounds** et **SetBounds** ont été utilisés pour interroger et manipuler l'étendue d'un élément \(les membres de **gauche** et de **top** sont toujours zéro\).  Dans MFC\/OLE 2 c'est plus directement pris en charge par `COleClientItem::GetExtent` et `SetExtent`, en **TAILLE** ou `CSize` à la place.  
  
 Le code de vos nouveaux appels SetItemRectToServer, et UpdateItemRectFromServer ressemble à ceci :  
  
```  
BOOL CRectItem::UpdateItemRectFromServer()  
{  
   ASSERT(m_bTrackServerSize);  
   CSize size;  
   if (!GetExtent(&size))  
      return FALSE;    // blank  
  
   // map from HIMETRIC to screen coordinates  
   {  
      CClientDC screenDC(NULL);  
      screenDC.SetMapMode(MM_HIMETRIC);  
      screenDC.LPtoDP(&size);  
   }  
   // just set the item size  
   if (m_rect.Size() != size)  
   {  
      // invalidate the old size/position  
      Invalidate();  
      m_rect.right = m_rect.left + size.cx;  
      m_rect.bottom = m_rect.top + size.cy;  
      // as well as the new size/position  
      Invalidate();  
   }  
   return TRUE;  
}  
  
BOOL CRectItem::SetItemRectToServer()  
{  
   // set the official bounds for the embedded item  
   CSize size = m_rect.Size();  
   {  
      CClientDC screenDC(NULL);  
      screenDC.SetMapMode(MM_HIMETRIC);  
      screenDC.DPtoLP(&size);  
   }  
   TRY  
   {  
      SetExtent(size);  // may do a wait  
   }  
   CATCH(CException, e)  
   {  
      return FALSE;  // links will not allow SetBounds  
   }  
   END_CATCH  
   return TRUE;  
}  
  
\oclient\frame.cpp(50) : error C2039: 'InWaitForRelease' : is not a member of 'COleClientItem'  
\oclient\frame.cpp(50) : error C2065: 'InWaitForRelease' : undeclared identifier  
\oclient\frame.cpp(50) : error C2064: term does not evaluate to a function  
```  
  
 Dans les appels d'API MFC\/OLE1 synchrones d'un conteneur à un serveur *ayant été simulés*, car OLE1 est fondamentalement asynchrone dans de nombreux cas.  Il est nécessaire de vérifier un appel asynchrone en attente en cours avant de traiter des commandes de l'utilisateur.  MFC\/OLE1 a fourni la fonction de **COleClientItem::InWaitForRelease** pour cela.  Dans MFC\/OLE 2 ce n'est pas nécessaire, vous pouvez supprimer toute la substitution de OnCommand dans CMainFrame ensemble.  
  
 À ce stade OCLIENT compilera et le liera.  
  
## D'autres modifications nécessaires  
 Il y a peu d'éléments qui ne sont pas effectuées qui conservent OCLIENT d'exécution, toutefois.  Il est préférable de résoudre ces problèmes maintenant plutôt qu'ensuite.  
  
 En premier lieu, il est nécessaire d'initier les bibliothèques OLE.  Cela s'effectue en appelant **AfxOleInit** à partir de `InitInstance`:  
  
```  
if (!AfxOleInit())  
{  
  AfxMessageBox("Failed to initialize OLE libraries");  
  return FALSE;  
}  
```  
  
 Il serait également judicieux de vérifier les fonctions virtuelles des modifications de la liste de paramètres.  Une telle fonction est `COleClientItem::OnChange`, remplacée dans chaque application conteneur de MFC\/OLE.  En examinant l'aide en ligne, vous pouvez constater que les coûts supplémentaires « dwParam DWORD » ont été ajoutés.  Le nouveau CRectItem::OnChange ressemble à ce qui suit :  
  
```  
void   
CRectItem::OnChange(OLE_NOTIFICATION wNotification, DWORD dwParam)  
{  
  if (m_bTrackServerSize &&  
        !UpdateItemRectFromServer())  
  {  
    // Blank object  
    if (wNotification == OLE_CLOSED)  
    {  
      // no data received for the object - destroy it  
      ASSERT(!IsVisible());  
      GetDocument()->DeleteItem(this);  
      return;   // no update (item is gone now)  
    }  
  }  
  if (wNotification != OLE_CLOSED)  
      Dirty();  
  Invalidate();  // any change will cause a redraw  
}  
```  
  
 Dans MFC\/OLE1, les applications conteneur font dériver la classe de document de **COleClientDoc**.  Dans MFC\/OLE 2 cette classe a été supprimée et remplacée par `COleDocument` \(cette nouvelle planification simplifie créer des applications conteneur\/serveur\).  Il existe `#define` mappé **COleClientDoc** à `COleDocument` pour simplifier le portage des applications MFC\/OLE1 de MFC\/OLE 2, par exemple OCLIENT.  L'une des fonctionnalités non disponibles par `COleDocument` fournie par **COleClientDoc** sont les entrées de la table des messages standard de commande.  Ceci afin que les applications serveur, qui utilisent également `COleDocument` \(ou\), ne retiennent pas la charge de ces gestionnaires de commandes sauf s'il y a une application conteneur\/serveur.  Vous devez également ajouter les entrées suivantes au mappage de messages CMainDoc:  
  
```  
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE, OnUpdatePasteMenu)  
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE_LINK, OnUpdatePasteLinkMenu)  
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_LINKS, OnUpdateEditLinksMenu)  
ON_COMMAND(ID_OLE_EDIT_LINKS, COleDocument::OnEditLinks)  
ON_UPDATE_COMMAND_UI(ID_OLE_VERB_FIRST, OnUpdateObjectVerbMenu)  
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_CONVERT, OnUpdateObjectVerbMenu)  
ON_COMMAND(ID_OLE_EDIT_CONVERT, OnEditConvert)  
```  
  
 L'implémentation de toutes les commandes est dans `COleDocument`, qui est la classe de base pour votre document.  
  
 À ce stade, OCLIENT est une application de conteneur OLE fonctionnelle.  Il est possible d'insérer des éléments de tout type \(OLE OLE1 ou 2\).  Étant donné que le code nécessaire pour activer l'activation sur place n'est pas implémentée, les éléments sont modifiés dans une fenêtre distincte comme avec OLE1.  La section suivante décrit les modifications nécessaires pour activer la modification sur place \(parfois appelée « modification sur place »\).  
  
## L'ajout de la « modification sur place »  
 Une des fonctionnalités intéressantes OLE est activation sur place \(ou « modification sur place »\).  Cette fonctionnalité permet à l'application serveur pour fournir des éléments de l'interface utilisateur du conteneur fournissait une interface plus transparente de modification de l'utilisateur.  Pour implémenter l'activation sur place à OCLIENT, certaines ressources spéciales doivent être ajoutées, ainsi qu'un code supplémentaire.  Ces ressources et le code sont normalement fournis par AppWizard — en fait, une grande partie de code ici était emprunté directement à une application AppWizard avec prise en charge du "conteneur".  
  
 Tout d'abord, il est nécessaire d'ajouter une ressource menu à utiliser lorsqu'il y a un élément qui est actif sur place.  Vous pouvez créer cette ressource menu supplémentaires dans Visual C\+\+ en copiant la ressource IDR\_OCLITYPE et en supprimant toutes les valeurs sauf dans le fichier et la fenêtre POP\- UPS.  Deux barres de séparation sont insérées entre le fichier et la fenêtre POP\- UPS pour afficher la séparation des groupes \(il doit examiner le suit : Fichier &#124; &#124; Fenêtre\).  Pour plus d'informations sur ce que signifient ces séparateurs et comment les menus du serveur et conteneurs sont fusionnés, consultez « menus et des ressources : Fusion de menus » dans *OLE 2 classes*.  
  
 Une fois que vous avez créé ces menus, vous devez en informer l'infrastructure.  Cela s'effectue en appelant `CDocTemplate::SetContainerInfo` pour le modèle de document avant de l'ajouter à la liste modèle de document dans votre InitInstance.  Nouveau code pour enregistrer les termes modèle de document ressemble à ceci :  
  
```  
CDocTemplate* pTemplate = new CMultiDocTemplate(  
    IDR_OLECLITYPE,  
    RUNTIME_CLASS(CMainDoc),  
    RUNTIME_CLASS(CMDIChildWnd),    // standard MDI child frame  
    RUNTIME_CLASS(CMainView));  
pTemplate->SetContainerInfo(IDR_OLECLITYPE_INPLACE);  
AddDocTemplate(pTemplate);  
```  
  
 La ressource IDR\_OLECLITYPE\_INPLACE est la ressource sur place spéciale créée dans Visual C\+\+.  
  
 Pour activer l'activation sur place, il existe quelques éléments qui doivent les modifier dans la classe dérivée à `CView` \(CMainView\) ainsi qu' `COleClientItem` dérivé fichier \(CRectItem\).  Toutes ces substitutions sont fournies par AppWizard et la plupart de l'implémentation sera directement à partir d'une application par défaut d'AppWizard.  
  
 Dans la première étape de ce port, l'activation sur place a été désactivée entièrement en remplaçant `COleClientItem::CanActivate`.  Ce fichier doit être supprimé pour permettre l'activation sur place.  En outre, la valeur NULL a été passée à tous les appels à `DoVerb` \(il existe deux d'entre eux\) car la fourniture de la vue est uniquement nécessaire pour l'activation sur place.  Pour implémenter complètement l'activation sur place, il est nécessaire de passer la vue appropriée dans l'appel `DoVerb`.  Un de ces appels se trouve dans **CMainView::OnInsertObject**:  
  
```  
pItem->DoVerb(OLEIVERB_SHOW, this);  
```  
  
 Un autre dans **CMainView::OnLButtonDblClk**:  
  
```  
m_pSelection->DoVerb(OLEIVERB_PRIMARY, this);  
```  
  
 Il est nécessaire de remplacer `COleClientItem::OnGetItemPosition`.  Cela indique le serveur sur lequel mettre sa fenêtre par rapport à la fenêtre du conteneur lorsque l'élément est activé sur place.  Pour OCLIENT, l'implémentation est triviale :  
  
```  
void CRectItem::OnGetItemPosition(CRect& rPosition)  
{  
    rPosition = m_rect;  
}  
```  
  
 La plupart des serveurs implémentent également ce qui est appelé « redimensionnement sur place. » Cela permet à la fenêtre de serveur de classer et d'être déplacées lorsque l'utilisateur modifie l'élément.  Le conteneur peut participer à cette action, depuis déplacer ou redimensionner la fenêtre affecte généralement la position et la taille du document conteneur elle\-même.  L'implémentation de OCLIENT synchroniser le rectangle interne détenu par le m\_rect avec la nouvelle position et la taille.  
  
```  
BOOL CRectItem::OnChangeItemPosition(const CRect& rectPos)  
{  
    ASSERT_VALID(this);  
  
    if (!COleClientItem::OnChangeItemPosition(rectPos))  
        return FALSE;  
  
    Invalidate();  
    m_rect = rectPos;  
    Invalidate();  
    GetDocument()->SetModifiedFlag();  
  
    return TRUE;  
}  
```  
  
 À ce stade, il y a suffisamment de code pour permettre à un élément d'être activé sur place et traiter le dimensionnement et déplacer l'élément lorsqu'il est actif, mais aucun code ne permet à l'utilisateur pour fermer la session d'édition.  Bien que certains serveurs fournissent cette fonctionnalité eux\-mêmes gérer la touche ESCAPE, il suggère que les conteneurs proposent deux méthodes pour désactiver un élément : \(1\) en cliquant sur l'extérieur de l'élément, et \(2\) en appuyant sur la touche ESCAPE.  
  
 Pour la clé ESCAPE, ajoutez une limitation dans Visual C\+\+ qui mappe la clé de VK\_ESCAPE à une commande, ID\_CANCEL\_EDIT est ajouté aux ressources.  Le responsable de cette commande suivante :  
  
```  
// The following command handler provides the standard  
// keyboard user interface to cancel an in-place  
// editing session.void CMainView::OnCancelEdit()  
{  
    // Close any in-place active item on this view.  
    COleClientItem* pActiveItem =   
        GetDocument()->GetInPlaceActiveItem(this);  
    if (pActiveItem != NULL)  
        pActiveItem->Close();  
    ASSERT(GetDocument()->GetInPlaceActiveItem(this) == NULL);  
}  
```  
  
 Pour traiter le cas lorsque l'utilisateur clique sur l'extérieur de l'élément, vous ajoutez le code suivant au début de **CMainView::SetSelection**:  
  
```  
if (pNewSel != m_pSelection || pNewSel == NULL)  
{  
    COleClientItem* pActiveItem =   
        GetDocument()->GetInPlaceActiveItem(this);  
    if (pActiveItem != NULL && pActiveItem != pNewSel)  
        pActiveItem->Close();  
}  
  
```  
  
 Lorsqu'un élément est actif sur place, il doit avoir le focus.  Pour vérifier si cela est le cas, gérez OnSetFocus afin que le focus soit toujours transféré à l'élément actif lorsque votre vue reçoit le focus :  
  
```  
// Special handling of OnSetFocus and OnSize are required   
// when an object is being edited in-place.  
void CMainView::OnSetFocus(CWnd* pOldWnd)  
{  
    COleClientItem* pActiveItem =   
        GetDocument()->GetInPlaceActiveItem(this);  
    if (pActiveItem != NULL &&  
    pActiveItem->GetItemState() == COleClientItem::activeUIState)  
    {  
        // need to set focus to this item if it is same view  
        CWnd* pWnd = pActiveItem->GetInPlaceWindow();  
        if (pWnd != NULL)  
        {  
            pWnd->SetFocus();  // don't call the base class  
            return;  
        }  
    }  
  
    CView::OnSetFocus(pOldWnd);  
}  
```  
  
 Lorsque la vue est redimensionnée, vous devez indiquer l'élément actif sur lequel le rectangle de secteur a changé.  Pour cela, vous fournissez un gestionnaire de `OnSize`:  
  
```  
void CMainView::OnSize(UINT nType, int cx, int cy)  
{  
    CView::OnSize(nType, cx, cy);  
    COleClientItem* pActiveItem =   
        GetDocument()->GetInPlaceActiveItem(this);  
    if (pActiveItem != NULL)  
        pActiveItem->SetItemRects();  
}  
```  
  
## Étude de cas : HIERSVR de MFC 2,0  
 [HIERSVR](../top/visual-cpp-samples.md) a également été inclus dans MFC 2,0 et implémenté avec OLE MFC\/OLE1.  Cette remarque décrit brièvement les étapes par lesquelles cette application a été initialement convertie d'utiliser MFC\/OLE 2 classes.  Plusieurs fonctions ont été ajoutées uniquement après que le port initial a été réglé pour illustrer le mieux les classes de MFC\/OLE 2.  Ces fonctionnalités ne sont pas couvertes ici ; reportez\-vous à l'exemple lui\-même pour plus d'informations sur les fonctionnalités avancées.  
  
> [!NOTE]
>  L'opération des erreurs de compilation étape par étape a été créée avec Visual C\+\+ 2.0.  Les messages d'erreur et les emplacements peuvent avoir changé avec Visual C\+\+ 4,0, mais les informations conceptuelles restent valides.  
  
## Les obtention de service  
 L'approche adoptée pour déplacer l'exemple de HIERSVR de MFC\/OLE est de commencer par le générer et résoudre des erreurs de compilateur évidentes qui résulteront.  Si vous prélevez l'exemple de HIERSVR à partir de MFC 2,0 et le compilez avec cette version de MFC, vous constaterez qu'il n'y a pas de nombreuses erreurs à résoudre \(bien qu'il y a plus que avec l'exemple de OCLIENT\).  Les erreurs dans l'ordre dans lequel elles se sont produites habituellement, sont décrites ci\-dessous.  
  
## Compile et répare les erreurs  
  
```  
\hiersvr\hiersvr.cpp(83) : error C2039: 'RunEmbedded' : is not a member of 'COleTemplateServer'  
```  
  
 Cette première erreur exacte un problème beaucoup plus important à la fonction `InitInstance` pour les serveurs.  L'initialisation requise pour un serveur OLE est probablement l'une des plus grandes modifications que vous devrez apporter à votre application MFC\/OLE1 de l'obtention de l'exécution.  La meilleure chose à faire est de rechercher ce qu'AppWizard crée pour un serveur OLE et modifier votre code comme il convient.  Voici quelques points à prendre en compte :  
  
 Il est nécessaire d'initialisation OLE les bibliothèques en appelant **AfxOleInit**  
  
 Appelle SetServerInfo sur l'objet modèle de document les informations définies de handles et de classe runtime des ressources du serveur que vous ne pouvez pas définir avec le constructeur `CDocTemplate`.  
  
 Ne pas afficher la fenêtre principale de votre application si \/Embedding est présent dans la ligne de commande.  
  
 Vous aurez besoin de **GUID** de votre document.  Il s'agit d'un identificateur unique pour le type de document \(128 bits\).  Crée un AppWizard automatiquement — si vous utilisez les techniques décrites ici pour copier un nouveau code d'une application serveur générée par AppWizard, vous pouvez simplement "voler" le GUID de cette application.  Sinon, vous pouvez utiliser l'utilitaire de GUIDGEN.EXE dans le répertoire bin.  
  
 Il est nécessaire de « connecter » votre objet `COleTemplateServer` au modèle de document en appelant `COleTemplateServer::ConnectTemplate`.  
  
 Mettez à jour le registre système lorsque votre application autonome est exécutée.  De cette façon, si l'utilisateur est le .EXE pour votre application, l'exécution de son nouvel emplacement met à jour la base de données d'inscription système Windows pour afficher le nouvel emplacement.  
  
 Après avoir appliqué toutes ces modifications sur lesquelles AppWizard créé pour `InitInstance`, `InitInstance` \(le GUID associé\) pour HIERSVR doit lire les suivantes :  
  
```  
// this is the GUID for HIERSVR documents  
static const GUID BASED_CODE clsid =  
    { 0xA0A16360L, 0xC19B, 0x101A, { 0x8C, 0xE5, 0x00, 0xDD, 0x01, 0x11, 0x3F, 0x12 } };  
  
/////////////////////////////////////////////////////////////////////////////  
// COLEServerApp initialization  
  
BOOL COLEServerApp::InitInstance()  
{  
    // OLE 2 initialization  
    if (!AfxOleInit())  
    {  
        AfxMessageBox("Initialization of the OLE failed!");  
        return FALSE;  
    }  
  
    // Standard initialization  
    LoadStdProfileSettings(); // Load standard INI file options   
  
    // Register document templates  
    CDocTemplate* pDocTemplate;  
    pDocTemplate = new CMultiDocTemplate(IDR_HIERSVRTYPE,  
        RUNTIME_CLASS(CServerDoc),     
        RUNTIME_CLASS(CMDIChildWnd),  
        RUNTIME_CLASS(CServerView));  
    pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB);  
    AddDocTemplate(pDocTemplate);  
  
    // create main MDI Frame window  
    CMainFrame* pMainFrame = new CMainFrame;  
    if (!pMainFrame->LoadFrame(IDR_MAINFRAME))  
        return FALSE;  
    m_pMainWnd = pMainFrame;  
  
    SetDialogBkColor();   // gray look  
  
    // enable file manager drag/drop and DDE Execute open  
    m_pMainWnd->DragAcceptFiles();  
    EnableShellOpen();  
  
    m_server.ConnectTemplate(clsid, pDocTemplate, FALSE);  
    COleTemplateServer::RegisterAll();  
  
    // try to launch as an OLE server  
    if (RunEmbedded())  
    {  
        // "short-circuit" initialization -- run as server!  
        return TRUE;  
    }  
    m_server.UpdateRegistry();  
    RegisterShellFileTypes();  
  
    // not run as OLE server, so show the main window  
    if (m_lpCmdLine[0] == '\0')  
    {  
        // create a new (empty) document  
        OnFileNew();  
    }  
    else  
    {  
        // open an existing document  
        OpenDocumentFile(m_lpCmdLine);  
    }  
  
    pMainFrame->ShowWindow(m_nCmdShow);  
    pMainFrame->UpdateWindow();  
  
    return TRUE;  
}  
```  
  
 Vous remarquerez que code ci\-dessus fait référence à un nouvel ID de ressource, IDR\_HIERSVRTYPE\_SRVR\_EMB.  Il s'agit de la ressource menu à utiliser lorsqu'un document incorporé dans un autre conteneur est modifié.  Dans MFC\/OLE1 les éléments de menu spécifiques à modifier un élément incorporé ont été modifiés activé.  Utilisation d'une structure de menu complètement différente en modifiant un élément incorporé au lieu de modifier un document basé sur des fichiers simplifie beaucoup pour fournir différentes interfaces utilisateur pour ces deux modes différents.  Comme vous pourrez le constater, une ressource de menu entièrement séparée est utilisée lors de l'édition d'un objet incorporé dans l'emplacement.  
  
 Pour créer cette ressource, chargez le script de ressources dans Visual C\+\+ et copiez la ressource existante du menu IDR\_HIERSVRTYPE.  Renommez la nouvelle ressource à IDR\_HIERSVRTYPE\_SRVR\_EMB \(il s'agit de la même convention d'affectation des noms qui utilise pour AppWizard\).  Modification suivante « sauvegarde de fichiers » dans la section « mise à jour de fichiers » ; attribuez \-lui l'ID de commande **ID\_FILE\_UPDATE**.  Modifiez également la « sauvegarde de fichier comme suit » « classer la sauvegarde comme » ; attribuez \-lui l'ID de commande **ID\_FILE\_SAVE\_COPY\_AS**.  L'infrastructure fournit l'implémentation des deux commandes.  
  
```  
\hiersvr\svritem.h(60) : error C2433: 'OLESTATUS' : 'virtual' not permitted on data declarations  
\hiersvr\svritem.h(60) : error C2501: 'OLESTATUS' : missing decl-specifiers  
\hiersvr\svritem.h(60) : error C2146: syntax error : missing ';' before identifier 'OnSetData'  
\hiersvr\svritem.h(60) : error C2061: syntax error : identifier 'OLECLIPFORMAT'  
\hiersvr\svritem.h(60) : error C2501: 'OnSetData' : missing decl-specifiers  
```  
  
 Il existe de nombreuses erreurs résultant de la substitution de `OnSetData`, car elle fait référence au type **OLESTATUS**.  **OLESTATUS** a les erreurs retournées par OLE1 de partitionnement.  Cela a changé à `HRESULT` dans OLE 2, bien que convertisse MFC généralement `HRESULT` dans `COleException` contenant l'erreur.  Dans ce cas, la substitution de `OnSetData` n'est plus nécessaire, la table la plus facile à faire est de le supprimer.  
  
```  
\hiersvr\svritem.cpp(30) : error C2660: 'COleServerItem::COleServerItem' : function does not take 1 parameters  
```  
  
 Le constructeur `COleServerItem` prend un paramètre supplémentaire 'BOOL'.  Cet indicateur détermine comment la gestion de la mémoire est effectuée sur les objets `COleServerItem`.  En définissant la VALEUR TRUE, l'infrastructure gère la gestion de la mémoire de ces objets \- les supprimer lorsqu'ils ne sont plus nécessaires.  HIERSVR utilise des objets de **CServerItem** \(dérivé de `COleServerItem`\) dans le cadre de ses données natives, vous allez définir cette valeur FALSE.  Cela permet HIERSVR déterminer si chaque élément du serveur est supprimé.  
  
```  
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class  
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class  
```  
  
 Lorsque ces erreurs impliquent que, certaines fonctions « purement\- virtuelles » qui n'ont pas été remplacées dans CServerItem.  Très probablement cela est dû au fait que la liste des paramètres d'OnDraw a changé.  Pour corriger cette erreur, remplacez **CServerItem::OnDraw** comme suit \(ainsi que la déclaration dans svritem.h\) :  
  
```  
BOOL CServerItem::OnDraw(CDC* pDC, CSize& rSize)  
{  
    // request from OLE to draw node  
    pDC->SetMapMode(MM_TEXT); // always in pixels  
    return DoDraw(pDC, CPoint(0,0), FALSE);  
}  
```  
  
 Le nouveau paramètre est 'rSize'.  Cela vous permet de finaliser la taille de dessin, si pratique.  Cette taille doit être dans **HIMETRIC**.  Dans ce cas, il n'est pas pratique pour effectuer cette valeur, l'infrastructure appelle `OnGetExtent` pour récupérer l'extension.  Pour que fonctionne, vous devez implémenter `OnGetExtent`:  
  
```  
BOOL CServerItem::OnGetExtent(DVASPECT dwDrawAspect, CSize& rSize)  
{  
    if (dwDrawAspect != DVASPECT_CONTENT)  
        return COleServerItem::OnGetExtent(dwDrawAspect, rSize);  
  
    rSize = CalcNodeSize();  
    return TRUE;  
}  
  
\hiersvr\svritem.cpp(104) : error C2065: 'm_rectBounds' : undeclared identifier  
\hiersvr\svritem.cpp(104) : error C2228: left of '.SetRect' must have class/struct/union type  
\hiersvr\svritem.cpp(106) : error C2664: 'void __pascal __far DPtoLP(struct ::tagPOINT __far *,int )__far const ' : cannot convert parameter 1 from 'int __far *' to 'struct ::tagPOINT __far *'  
```  
  
 Dans la fonction de CServerItem::CalcNodeSize la taille de l'élément est convertie en **HIMETRIC** et stockée dans **m\_rectBounds**.  Le membre non documenté '**m\_rectBounds**' de `COleServerItem` n'existe pas \(il a été partiellement remplacée par `m_sizeExtent`, mais dans OLE 2 ce membre a une utilisation légèrement différente de **m\_rectBounds** apportées dans OLE1\).  Au lieu de définir la taille de **HIMETRIC** à cette variable membre, elle sans quoi retourne.  Cette valeur de retour est utilisée dans `OnGetExtent`, implémenté précédemment.  
  
```  
CSize CServerItem::CalcNodeSize()  
{  
    CClientDC dcScreen(NULL);  
  
    m_sizeNode = dcScreen.GetTextExtent(m_strDescription,  
      m_strDescription.GetLength());  
    m_sizeNode += CSize(CX_INSET * 2, CY_INSET * 2);  
  
    // set suggested HIMETRIC size  
    CSize size(m_sizeNode.cx, m_sizeNode.cy);  
    dcScreen.SetMapMode(MM_HIMETRIC);  
    dcScreen.DPtoLP(&size);  
    return size;  
}  
```  
  
 CServerItem remplace également **COleServerItem::OnGetTextData**.  Cette fonction est obsolète dans MFC\/OLE et est remplacée par un autre mécanisme.  La version de MFC 3,0 de liaison et incorporation d'objets MFC [HIERSVR](../top/visual-cpp-samples.md) implémente cette fonctionnalité en remplaçant `COleServerItem::OnRenderFileData`.  Cette fonctionnalité n'est pas importante pour ce port de base, vous pouvez supprimer la substitution de OnGetTextData.  
  
 Il existe davantage d'erreurs dans svritem.cpp qui n'ont pas été traités.  Ils ne sont pas « true » — erreurs uniquement erreurs dues à des erreurs précédentes.  
  
```  
\hiersvr\svrview.cpp(325) : error C2660: 'CopyToClipboard' : function does not take 2 parameters  
```  
  
 `COleServerItem::CopyToClipboard` ne prend plus en charge la balise « bIncludeNative ».  Les données native \(les données écrites dans l'élément du serveur sérialisation la fonction\) est toujours copiées, vous supprime le premier paramètre.  En outre, `CopyToClipboard` lève une exception lorsqu'une erreur se produit au lieu de retourner la valeur est FALSE.  Modifiez le code pour CServerView::OnEditCopy comme suit :  
  
```  
void CServerView::OnEditCopy()  
{  
    if (m_pSelectedNode == NULL)  
        AfxThrowNotSupportedException();  
  
    TRY  
    {  
        m_pSelectedNode->CopyToClipboard(TRUE);  
    }  
    CATCH_ALL(e)  
    {  
        AfxMessageBox("Copy to clipboard failed");  
    }  
    END_CATCH_ALL     
}  
```  
  
 Bien qu'il y ait eu plus d'erreurs résultant de la compilation de MFC 2,0 de HIERSVR qu'il y a de la même version de OCLIENT, il y a réellement moins modifications.  
  
 À ce stade HIERSVR compilera et le liera et fonctionne comme serveur OLE, mais sans fonctionnalités de modification sur place, qui est implémenté suivante.  
  
## L'ajout de la « modification sur place »  
 Pour ajouter la « modification sur place » \(ou l'activation sur place\) à cette application serveur, il existe quelques éléments que vous devez prendre soin de :  
  
-   Vous avez besoin d'une ressource particulière menu pour être utilisée lorsque l'élément est active sur place.  
  
-   Cette application comporte une barre d'outils, vous aurez besoin d'une barre d'outils uniquement un sous\-ensemble de la barre d'outils standard pour faire correspondre les commandes de menu disponibles à partir de le serveur \(correspond à la ressource menu mentionnée ci\-dessus\).  
  
-   Vous avez besoin d'une nouvelle classe dérivée de `COleIPFrameWnd` qui fournit l'interface utilisateur sur place \(comme CMainFrame, dérivé de `CMDIFrameWnd`, fournit l'interface utilisateur MDI\).  
  
-   Vous devez indiquer l'infrastructure sur ces ressources et les classes spéciales.  
  
 Il est facile de créer la ressource menu.  Exécutez Visual C\+\+, copiez la ressource menu IDR\_HIERSVRTYPE à une ressource menu appelée IDR\_HIERSVRTYPE\_SRVR\_IP.  Modifiez le menu afin que les messages uniquement des modifications et de menu ? \(aide\) sont autorisés.  Ajoutez deux séparateurs dans le menu entre la modification et les menus d'aide \(il doit examiner le suit : Modifier &#124; &#124; Aide\).  Pour plus d'informations sur ce que signifient ces séparateurs et comment les menus du serveur et conteneurs sont fusionnés, consultez « menus et des ressources : Fusion de menus » dans *OLE 2 classes*.  
  
 Le Bitmap de la barre d'outils de sous\-ensemble peut facilement être créée en copiant celui d'une application générée par AppWizard avec une option de «serveur» activée.  Cette bitmap peut être importée dans Visual C\+\+.  Veillez à donner à la bitmap un ID d'IDR\_HIERSVRTYPE\_SRVR\_IP.  
  
 La classe dérivée à `COleIPFrameWnd` peut également être copiées à partir d'une application générée par AppWizard avec prise en charge de serveur.  Copiez les deux fichiers, IPFRAME.CPP et IPFRAME.H et ajoutez\-les au projet.  Vérifiez que l'appel `LoadBitmap` fait référence à IDR\_HIERSVRTYPE\_SRVR\_IP, la bitmap créée à l'étape précédente.  
  
 Maintenant que toutes les nouvelles ressources et les classes sont créées, ajoutez le code nécessaire pour que l'infrastructure sache ces derniers \(et sait que l'application prend désormais en charge la modification sur place\).  Cette opération s'effectue en ajoutant encore plus de paramètres pour l'appel de `SetServerInfo` dans la fonction de `InitInstance` :  
  
```  
pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB,  
    IDR_HIERSVRTYPE_SRVR_IP, RUNTIME_CLASS(CInPlaceFrame));  
```  
  
 Il est maintenant sur place prêt à s'exécuter dans n'importe quel conteneur qui prend en charge l'activation sur place.  Cependant, il existe un bogue mineure flânant toujours dans le code.  HIERSVR prend en charge un menu contextuel, affiche lorsque l'utilisateur appuie sur le bouton droit de la souris.  Ce menu s'exécute lorsque HIERSVR est entièrement ouvert, mais ne fonctionne pas lorsque vous modifiez une incorporation sur place.  La raison peut être épinglée vers le bas jusqu'à la ligne de code dans CServerView::OnRButtonDown :  
  
```  
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,  
    point.x, point.y, AfxGetApp()->m_pMainWnd);  
```  
  
 Notez que la référence à **AfxGetApp\(\)\-\>m\_pMainWnd**.  Lorsque le serveur est activé sur place, il a une fenêtre principale et le m\_pMainWnd est défini, mais il est généralement invisible.  En outre, cette fenêtre fait référence à la fenêtre *principale* de l'application, la fenêtre cadre MDI qui s'affiche lorsque le serveur est entièrement ouvrir ou exécuter autonome.  Elle ne fait pas référence à la fenêtre du cadre actif — qui si sur place activé est une fenêtre cadre dérivée de `COleIPFrameWnd`.  Pour obtenir la fenêtre active appropriée quand la modification sur place, cette version de MFC ajoute une nouvelle fonctionnalité, `AfxGetMainWnd`.  En règle générale, vous devez utiliser cette fonction au lieu de **AfxGetApp\(\)\-\>m\_pMainWnd**.  Ce code doit changer les suivantes :  
  
```  
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,  
    point.x, point.y, AfxGetMainWnd());  
```  
  
 Maintenant vous avez un serveur OLE au minimum activé pour l'activation sur place fonctionnelle.  Mais il reste encore de nombreuses fonctionnalités disponibles avec MFC\/OLE 2 qui n'étaient pas encore disponibles dans MFC\/OLE1.  Consultez l'exemple de HIERSVR pour des idées sur les fonctionnalités que vous pouvez implémenter.  Certaines fonctionnalités que HIERSVR implémente sont répertoriées ci\-dessous :  
  
-   Zoomant, pour le comportement de vrais WYSISYG par rapport à le conteneur.  
  
-   Faites glisser\/suppression et un format personnalisé du presse\-papiers.  
  
-   Faites défiler la fenêtre de conteneur comme sélection est modifié.  
  
 L'exemple de HIERSVR de MFC 3,0 utilise également une conception légèrement différente pour les éléments du serveur.  Cela permet d'économiser la mémoire et rend les liens plus flexibles.  Avec la version 2,0 de HIERSVR chaque nœud de l'arborescence *AIS* `COleServerItem`.  `COleServerItem` inclut un peu plus de surcharge qu'est strictement nécessaire pour chacun de ces nœuds, mais `COleServerItem` est requis pour chaque lien actif.  Mais dans la plupart des cas, il y a peu de liens actifs à un moment donné.  Pour effectuer cela plus efficace, le HIERSVR dans cette version de MFC sépare le nœud de `COleServerItem`.  Il a un CServerNode et une classe de **CServerItem**.  **CServerItem** \(dérivé de `COleServerItem`\) est uniquement créé selon les besoins.  Une fois l'arrêt du conteneur \(ou conteneurs\) à l'aide de ce lien particulier vers ce nœud particulier, l'objet de CServerItem associé au CServerNode est supprimé.  Cette conception est plus efficace et plus souple.  La flexibilité est disponible en lors de le traitement des liens de sélection multiple.  Il est beaucoup plus facile à aucun de ces deux versions de sélection multiple de support de HIERSVR, mais est \(et des supports à ces sélections\) avec la version de MFC 3,0 de HIERSVR, car `COleServerItem` est séparé des données natives.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)
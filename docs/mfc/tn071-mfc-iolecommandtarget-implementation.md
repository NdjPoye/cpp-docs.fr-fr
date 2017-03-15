---
title: "TN071&#160;: Impl&#233;mentation IOleCommandTarget MFC | Microsoft Docs"
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
  - "IOleCommandTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interface IOleCommandTarget"
  - "TN071"
ms.assetid: 3eef571e-6357-444d-adbb-6f734a0c3161
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN071&#160;: Impl&#233;mentation IOleCommandTarget MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 L'interface `IOleCommandTarget` permet aux objets et leurs conteneurs de distribuer des commandes entre eux.  Par exemple, les barres d'outils d'un objet peuvent contenir des boutons pour les commandes telles que **Impression**, **Aperçu avant impression**, **Enregistrer**, `New`, et **Zoom**.  Si un tel objet a été incorporé dans un conteneur qui prend en charge `IOleCommandTarget`, l'objet pourrait activer les boutons et transférer les commandes au conteneur pour traitement lorsque l'utilisateur les a cliquées.  Si un conteneur souhaitait que l'objet incorporé s'imprime, il peut en faire la requête en envoyant une commande via l'interface `IOleCommandTarget` de l'objet incorporé.  
  
 `IOleCommandTarget` est une interface de type Automation parce qu'elle est utilisée par un client pour invoquer des méthodes sur un serveur.  Toutefois, l'utilisation de `IOleCommandTarget` enregistre la surcharge de faire des appels via des interfaces Automation car les programmeurs ne doivent pas utiliser la méthode classique coûteuse `Invoke` de `IDispatch`.  
  
 Dans MFC, l'interface `IOleCommandTarget` est utilisée par les serveurs de documents actifs pour permettre aux conteneurs de documents actifs d'envoyer des commandes au serveur.  La classe de serveur de document actif, `CDocObjectServerItem`, utilise le mappage d'interface MFC \(voir [TN038 : Implémentation de IUnknown dans MFC\/OLE](../mfc/tn038-mfc-ole-iunknown-implementation.md)\) pour implémenter l'interface `IOleCommandTarget`.  
  
 `IOleCommandTarget` est également implémentée dans la classe **COleFrameHook**.  **COleFrameHook** est une classe non documentée de MFC qui implémente les fonctionnalités d'affichage de cadre de modification des conteneurs en place.  **COleFrameHook** utilise également les mappages d'interface de MFC pour implémenter l'interface `IOleCommandTarget`.  L'implémentation de **COleFrameHook** de `IOleCommandTarget` transfère les commandes OLE à des conteneurs de documents actifs dérivés de `COleDocObjectItem`.  Cela permet à n'importe quel conteneur de documents actifs de MFC de recevoir les messages des serveurs de documents actifs contenus.  
  
## Carte de commande OLE MFC  
 Les développeurs MFC peuvent tirer parti de `IOleCommandTarget` à l'aide de cartes de commande OLE MFC.  Les cartes de commande OLE sont comme les tables des messages car elles peuvent être utilisées pour mapper des commandes OLE aux méthodes de la classe qui contient la carte de commande.  Pour faire fonctionner ceci, placez des macros dans la carte de commande pour spécifier le groupe OLE de commandes de la commande à gérer, la commande OLE, et l'ID de commande du message [WM\_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) qui sera envoyé lorsque la commande OLE est acceptée.  MFC fournit également plusieurs macros prédéfinies pour les commandes standard OLE.  Pour obtenir la liste des commandes standard OLE qui ont été initialement conçues pour une utilisation avec des applications Microsoft Office, consultez l'énumération d'OLECMDID, qui est définie dans docobj.h.  
  
 Lorsqu'une commande OLE est reçue par une application de MFC qui contient une carte de commande OLE, MFC tente de déterminer l'ID de commande et le groupe de commandes de la commande demandée dans la carte de commande OLE de l'application.  Si une correspondance est trouvée, un message **WM\_COMMAND** est distribué à l'application contenant la carte de commande avec l'ID de la commande demandée. \(Consultez la description de `ON_OLECMD` ci\-dessous\). De cette manière, les commandes OLE distribuées à une application sont transformées en messages de **WM\_COMMAND** par MFC.  Les messages **WM\_COMMAND** sont ensuite routés dans les tables des messages de l'application qui utilise l'architecture standard de MFC de [routage des commandes](../mfc/command-routing.md).  
  
 Contrairement aux tables de messages, les cartes de commande OLE MFC ne sont pas prises en charge par ClassWizard.  Les développeurs MFC doivent insérer la prise en charge des cartes de commande OLE et les entrées de mappage de commande OLE à la main.  Les cartes de commande OLE peuvent être ajoutées aux serveurs de documents actifs MFC dans n'importe quelle classe qui figure dans la chaîne de message\-routage de **WM\_COMMAND** pendant que le document actif est acfve sur place dans un conteneur.  Ces classes sont les classes de l'application dérivées de [CWinApp](../mfc/reference/cwinapp-class.md), [CView](../mfc/reference/cview-class.md), [CDocument](../mfc/reference/cdocument-class.md), et [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md).  Dans des conteneurs de documents actifs, les cartes de commande OLE peuvent être ajoutées à la classe dérivée de [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md).  De plus, dans les conteneurs de documents actifs, les messages **WM\_COMMAND** sont distribués uniquement à la table des messages dans la classe dérivée de `COleDocObjectItem`.  
  
## Macros de carte de commande OLE  
 Utilisez les macros suivantes pour ajouter la fonctionnalité de carte de commandes dans la classe :  
  
```  
  
DECLARE_OLECMD_MAP ()  
  
```  
  
 La macro entre dans la déclaration de classe \(généralement dans le fichier d'en\-tête\) de la classe qui contient la carte de commande.  
  
```  
  
BEGIN_OLECMD_MAP(  
theClass  
,   
baseClass  
)  
  
```  
  
 `theClass`  
 Nom complet de la classe qui contient le mappage de commande.  
  
 `baseClass`  
 Nom de la classe de base de la classe qui contient la carte de commande.  
  
 La macro marque le début de la carte de commande.  Utilisez la macro du fichier d'implémentation pour la classe qui contient la carte de commande.  
  
```  
  
END_OLECMD_MAP()  
  
```  
  
 La macro marque la fin de la carte de commande.  Utilisez la macro du fichier d'implémentation pour la classe qui contient la carte de commande.  La macro doit toujours respecter la macro de **BEGIN\_OLECMD\_MAP**.  
  
```  
  
ON_OLECMD(  
pguid  
,   
olecmdid  
,   
id  
)  
  
```  
  
 `pguid`  
 Pointeur vers le GUID du groupe de la commande OLE.  Ce paramètre est **NULL** pour le groupe de commandes standard OLE.  
  
 *olecmdid*  
 ID de commande OLE de la commande qui doit être appelé.  
  
 `id`  
 ID du message **WM\_COMMAND** à envoyer à l'application contenant la carte de commande OLE quand cette commande est appelée.  
  
 Utilisez la macro `ON_OLECMD` de la carte de commande pour ajouter des entrées pour les commandes OLE à gérer.  Lorsque les commandes OLE sont acceptées, elles sont converties au message spécifié de **WM\_COMMAND** et routées via la table des messages de l'application qui utilise l'architecture standard de routage des commandes de MFC.  
  
## Exemple  
 L'exemple suivant montre comment ajouter la fonction OLE de gestion de commande sur un serveur de document actif MFC pour gérer la commande OLE [OLECMDID\_PRINT](http://msdn.microsoft.com/library/windows/desktop/ms691264).  Cet exemple part du principe que vous avez utilisé AppWizard pour générer une application MFC qui est un serveur de document actif.  
  
1.  Dans votre fichier d'en\-tête dérivé de la classe `CView`, ajoutez la macro `DECLARE_OLECMD_MAP` de la déclaration de classe.  
  
    > [!NOTE]
    >  Utilisez la classe dérivée de `CView` car elle est l'une des classes du serveur du document actif qui figure dans la chaîne de message\-routage de **WM\_COMMAND**.  
  
    ```  
    class CMyServerView : public CView  
    {  
    protected: // create from serialization only  
       CMyServerView();  
       DECLARE_DYNCREATE(CMyServerView)  
       DECLARE_OLECMD_MAP()  
    . . .  
    };  
    ```  
  
2.  Dans le fichier d'implémentation pour la classe dérivée de `CView`, ajoutez les macros `BEGIN_OLECMD_MAP` et `END_OLECMD_MAP`:  
  
    ```  
    BEGIN_OLECMD_MAP(CMyServerView, CView)  
  
    END_OLECMD_MAP()  
    ```  
  
3.  Pour gérer la commande OLE d'imprimession standard, ajoutez une macro [ON\_OLECMD](../Topic/ON_OLECMD.md) à la carte de commande OLE en spécifiant l'ID de commande pour la commande d'imprimession standard et **ID\_FILE\_PRINT** pour l'ID de **WM\_COMMAND**.  **ID\_FILE\_PRINT** est l'ID de commande standard d'impression utilisé par les applications MFC générées par AppWizard:  
  
    ```  
    BEGIN_OLECMD_MAP(CMyServerView, CView)  
       ON_OLECMD(NULL,OLECMDID_PRINT,ID_FILE_PRINT)  
    END_OLECMD_MAP()  
    ```  
  
 Notez qu'une des macros de commande standard OLE, définie dans afxdocob.h, peut être utilisé à la place de la macro `ON_OLECMD` car **OLECMDID\_PRINT** est un identificateur standard OLE de commande.  La macro `ON_OLECMD_PRINT` accomplira la même tâche que la macro `ON_OLECMD` ci\-dessus.  
  
 Lorsqu'un conteneur d'application envoie au serveur une commande **OLECMDID\_PRINT** via l'interface `IOleCommandTarget` du serveur, le gestionnaire de commande d'impression sera appelé sur le serveur, et le serveur imprimera l'application.  Le code du conteneur de documents actifs pour appeler la commande d'impression ajoutée dans les étapes ci\-dessus est quelque chose qui ressemble à ceci :  
  
```  
void CContainerCntrItem::DoOleCmd()  
{  
   IOleCommandTarget *pCmd = NULL;  
   HRESULT hr = E_FAIL;  
   OLECMD ocm={OLECMDID_PRINT, 0};  
  
   hr = m_lpObject->QueryInterface(IID_IOleCommandTarget,reinterpret_cast<void**>(&pCmd));  
   if(FAILED(hr))  
      return;  
  
   hr = pCmd->QueryStatus(NULL, 1, &ocm, NULL);  
   if(SUCCEEDED(hr) && (ocm.cmdf & OLECMDF_ENABLED))  
   {  
      //Command is available and enabled so call it  
      COleVariant vIn;  
      COleVariant vOut;  
      hr = pCmd->Exec(NULL, OLECMDID_PRINT,  
 OLECMDEXECOPT_DODEFAULT, &vIn, &vOut);  
      ASSERT(SUCCEEDED(hr));  
   }  
   pCmd->Release();  
}  
```  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)
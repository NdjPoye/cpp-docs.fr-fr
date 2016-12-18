---
title: "TN065&#160;: prise en charge d&#39;une interface double pour les serveurs Automation OLE | Microsoft Docs"
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
  - "vc.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ACDUAL (exemple) (MFC)"
  - "Automation (serveurs), prise en charge de l'interface double"
  - "interfaces doubles, OLE (Automation)"
  - "TN065"
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN065&#160;: prise en charge d&#39;une interface double pour les serveurs Automation OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Cette note discute de comment ajouter la prise en charge d'interfaces doubles à un serveur Automation MFC.  L'exemple de [ACDUAL](../top/visual-cpp-samples.md) illustre la prise en charge des interfaces doubles, et l'exemple de code de cette remarque provient d'ACDUAL.  Les macros décrites dans cette remarque, par exemple `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, et `IMPLEMENT_DUAL_ERRORINFO`, font partie de l'exemple de ACDUAL et se trouvent dans. MFCDUAL.H.  
  
## Interfaces doubles  
 Bien que OLE Automation pour vous permettre d'implémenter une interface de `IDispatch`, une interface du VTBL, ou une double interface \(qui comprend les deux\), Microsoft recommande vivement d'implémenter des interfaces pour tous les objets accessibles OLE Automation.  Les doubles interfaces ont des avantages importants par rapport à les interfaces réservées ou uniquement VTBL de `IDispatch`:  
  
-   La liaison peut avoir lieu au moment de la compilation via l'interface de VTBL, ou à l'aide de `IDispatch`.  
  
-   Les contrôleurs OLE Automation qui peuvent utiliser l'interface de VTBL peuvent tirer parti de meilleures performances.  
  
-   Les contrôleurs OLE Automation existants qui utilisent l'interface de `IDispatch` continueront à fonctionner.  
  
-   Il est plus facile appeler l'interface en VTBL C\+\+.  
  
-   Des interfaces requises pour la compatibilité avec les fonctionnalités de prise en charge de l'objet Visual Basic.  
  
## Prise en charge de les interfaces d'ajout d'une classe basée CCmdTarget\-  
 Une double interface n'est vraiment qu'une interface personnalisée dérivée de `IDispatch`.  La méthode la plus simple pour implémenter la prise en charge des interfaces doubles dans une classe basée sur des `CCmdTarget`est d'abord d'implémenter l'interface de dispatch normale sur votre classe à l'aide de MFC et ClassWizard, puis d'ajouter l'interface personnalisée ultérieurement.  Dans la plupart des cas, l'implémentation de l'interface utilisateur personnalisée délèguera simplement à MFC `IDispatch` l'implémentation.  
  
 D'abord, modifiez le fichier d'ODL pour que votre serveur définisse des interfaces pour les objets.  Pour définir une double interface, vous devez utiliser une instruction de l'interface, au lieu de l'instruction ALTER `DISPINTERFACE` que les assistants Visual C\+\+ génèrent.  Plutôt que supprimer l'instruction existante de `DISPINTERFACE`, ajoutez une nouvelle instruction de l'interface.  En conservant la forme de `DISPINTERFACE`, vous pouvez continuer à utiliser ClassWizard pour ajouter des propriétés et des méthodes à votre objet, mais vous devez ajouter les propriétés et les méthodes équivalentes à l'instruction de votre interface.  
  
 Une instruction d'interface pour une double interface doit avoir les attributs de **OLEAUTOMATION** et de **DUAL**, et l'interface doit être dérivée de `IDispatch`.  Vous pouvez utiliser l'exemple de [GUIDGEN](../top/visual-cpp-samples.md) pour créer **IID** pour la double interface :  
  
```  
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick  
   oleautomation,  
   dual  
]  
interface IDualAClick : IDispatch  
  {  
  };  
```  
  
 Une fois que vous avez mis en place l'instruction de l'interface, commencez à ajouter les entrées des méthodes et des propriétés.  Pour des interfaces, vous devez réorganiser les listes de paramètres afin que les fonctions et méthodes d'accesseur dans la double interface retournent `HRESULT` et transmettent les valeurs retournées comme paramètres avec les attributs `[retval,out]`.  N'oubliez pas que pour les propriétés, vous devez ajouter une lecture\(`propget`\) et la fonction d'accès en écriture \(`propput`\) avec le même ID.  Par exemple :  
  
```  
[propput, id(1)] HRESULT text([in] BSTR newText);  
[propget, id(1)] HRESULT text([out, retval] BSTR* retval);  
```  
  
 Après avoir défini vos méthodes et propriétés, vous devez ajouter une référence à l'instruction d'interface dans l'instruction de la coclasse.  Par exemple :  
  
```  
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]  
coclass Document  
{  
   dispinterface IAClick;  
   [default] interface IDualAClick;  
};  
```  
  
 Une fois votre fichier d'ODL mis à jour, utilisez le mécanisme de mappage de l'interface de MFC pour définir une classe d'implémentation de la double interface dans la classe d'objets et effectuer les entrées correspondantes dans le mécanisme `QueryInterface` de MFC.  Vous avez besoin d'une entrée dans le bloc de `INTERFACE_PART` pour chaque entrée dans l'instruction d'interface d'ODL, en plus des entrées valides pour une interface de dispatch.  Chaque entrée d'ODL possédant l'attribut de **propput** a besoin d'une fonction nommée `put_propertyname`.  Chaque entrée d'ODL possédant l'attribut de **propget** a besoin d'une fonction nommée `get_propertyname`.  
  
 Pour définir une classe d'implémentation de votre double interface, ajoutez un bloc de `DUAL_INTERFACE_PART` à la définition de classe d'objets.  Par exemple :  
  
```  
BEGIN_DUAL_INTERFACE_PART(DualAClick, IDualAClick)  
  STDMETHOD(put_text)(THIS_ BSTR newText);  
  STDMETHOD(get_text)(THIS_ BSTR FAR* retval);  
  STDMETHOD(put_x)(THIS_ short newX);  
  STDMETHOD(get_x)(THIS_ short FAR* retval);  
  STDMETHOD(put_y)(THIS_ short newY);  
  STDMETHOD(get_y)(THIS_ short FAR* retval);  
  STDMETHOD(put_Position)(THIS_ IDualAutoClickPoint FAR* newPosition);  
  STDMETHOD(get_Position)(THIS_ IDualAutoClickPoint FAR* FAR* retval);  
  STDMETHOD(RefreshWindow)(THIS);  
  STDMETHOD(SetAllProps)(THIS_ short x, short y, BSTR text);  
  STDMETHOD(ShowWindow)(THIS);  
END_DUAL_INTERFACE_PART(DualAClick)  
```  
  
 Pour connecter la double interface du mécanisme de [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms687230) de MFC, ajoutez une entrée de `INTERFACE_PART` au mappage d'interface :  
  
```  
BEGIN_INTERFACE_MAP(CAutoClickDoc, CDocument)  
  INTERFACE_PART(CAutoClickDoc, DIID_IAClick, Dispatch)  
  INTERFACE_PART(CAutoClickDoc, IID_IDualAClick, DualAClick)  
END_INTERFACE_MAP()  
```  
  
 Ensuite, vous devez effectuer l'implémentation de l'interface.  Dans la plupart des cas, vous pourrez déléguer à l'implémentation existante de `IDispatch` de MFC.  Par exemple :  
  
```  
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::AddRef()  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   return pThis->ExternalAddRef();  
}  
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::Release()  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   return pThis->ExternalRelease();  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::QueryInterface(  
             REFIID iid, LPVOID* ppvObj)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   return pThis->ExternalQueryInterface(&iid, ppvObj);  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfoCount(  
            UINT FAR* pctinfo)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);  
   ASSERT(lpDispatch != NULL);  
   return lpDispatch->GetTypeInfoCount(pctinfo);  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfo(  
          UINT itinfo, LCID lcid, ITypeInfo FAR* FAR* pptinfo)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);  
   ASSERT(lpDispatch != NULL);  
   return lpDispatch->GetTypeInfo(itinfo, lcid, pptinfo);  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetIDsOfNames(  
       REFIID riid, OLECHAR FAR* FAR* rgszNames, UINT cNames,  
       LCID lcid, DISPID FAR* rgdispid)   
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);  
   ASSERT(lpDispatch != NULL);  
   return lpDispatch->GetIDsOfNames(riid, rgszNames, cNames,   
                                    lcid, rgdispid);  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::Invoke(  
    DISPID dispidMember, REFIID riid, LCID lcid, WORD wFlags,  
    DISPPARAMS FAR* pdispparams, VARIANT FAR* pvarResult,  
    EXCEPINFO FAR* pexcepinfo, UINT FAR* puArgErr)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);  
   ASSERT(lpDispatch != NULL);  
   return lpDispatch->Invoke(dispidMember, riid, lcid,  
                             wFlags, pdispparams, pvarResult,  
                             pexcepinfo, puArgErr);  
}  
```  
  
 Pour les méthodes d'objet et d'accesseur de propriété, vous devez effectuer l'implémentation.  Les fonctions de méthodes et de propriétés peuvent généralement déléguer aux méthodes générées par ClassWizard.  Toutefois, si vous installez des propriétés pour accéder aux variables directement, vous devez écrire du code pour obtenir\/placer la valeur dans la variable.  Par exemple :  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   // MFC automatically converts from Unicode BSTR to   
   // Ansi CString, if necessary...  
   pThis->m_str = newText;  
   return NOERROR;  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::get_text(BSTR* retval)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   // MFC automatically converts from Ansi CString to   
   // Unicode BSTR, if necessary...  
   pThis->m_str.SetSysString(retval);  
   return NOERROR;  
}  
```  
  
## Passage des pointeurs d'interface double ;  
 Passer le pointeur d'interface double n'est pas simple, surtout si vous devez appeler `CCmdTarget::FromIDispatch`.  `FromIDispatch` fonctionne uniquement sur les pointeurs de `IDispatch` de MFC.  Une méthode pour contourner ce problème consiste à rechercher l'installation le pointeur original `IDispatch` mis en place par MFC et de passer le pointeur vers les fonctions qui ont besoin.  Par exemple :  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_Position(  
      IDualAutoClickPoint FAR* newPosition)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDisp = NULL;  
   newPosition->QueryInterface(IID_IDispatch, (LPVOID*)&lpDisp);  
   pThis->SetPosition(lpDisp);  
   lpDisp->Release();  
   return NOERROR;  
}  
```  
  
 Avant de transmettre un nouveau du pointeur via la méthode de l'interface double, vous devrez peut\-être effectuer la conversion du pointeur de MFC `IDispatch` à votre pointeur d'interface double.  Par exemple :  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::get_Position(  
      IDualAutoClickPoint FAR* FAR* retval)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   LPDISPATCH lpDisp;  
   lpDisp = pThis->GetPosition();  
   lpDisp->QueryInterface(IID_IDualAutoClickPoint, (LPVOID*)retval);  
   return NOERROR;  
}  
```  
  
## Enregistrer la Librairie des Types de l'Application  
 AppWizard ne génère pas de code pour enregistrer la bibliothèque de types d'une application serveur OLE Automation par le système.  Lorsqu'il existe d'autres façons d'inscrire la bibliothèque de types, il est plus commode de faire en sorte que le registre de l'application enregistre la bibliothèque de types lorsqu'il met à jour ses informations de type OLE, c'est\-à\-dire chaque fois que l'application autonome est exécutée.  
  
 Pour inscrire la bibliothèque de types d'application chaque fois que l'application autonome est exécutée :  
  
-   Inclure AFXCTL.H dans le standard inclut le fichier d'en\-tête, STDAFX.H, pour accéder à la définition de la fonction `AfxOleRegisterTypeLib`.  
  
-   Dans la fonction `InitInstance` de votre application, recherchez l'appel à `COleObjectFactory::UpdateRegistryAll`.  Après cet appel, ajoutez un appel à `AfxOleRegisterTypeLib`, en spécifiant le **LIBID** correspondant à la bibliothèque de types, ainsi que le nom de votre bibliothèque de types :  
  
    ```  
    // When a server application is launched stand-alone, it is a good idea  
    // to update the system registry in case it has been damaged.  
    m_server.UpdateRegistry(OAT_DISPATCH_OBJECT);  
    COleObjectFactory::UpdateRegistryAll();  
    // DUAL_SUPPORT_START  
    // Make sure the type library is registered or dual interface won't work.  
    AfxOleRegisterTypeLib(AfxGetInstanceHandle(), LIBID_ACDual, _T("AutoClik.TLB"));  
    // DUAL_SUPPORT_END  
    ```  
  
## Modification des paramètres de génération de projet pour tenir compte des changements dans la bibliothèque de types ;  
 Pour modifier les paramètres de la génération d'un projet afin qu'un fichier d'en\-tête contenant des définitions de **UUID** soit généré par MkTypLib à chaque fois que la bibliothèque de types est reconstruite :  
  
1.  Dans le menu **Version**, cliquez sur **Paramètres**, puis sélectionnez le fichier d'ODL de la liste des fichiers à chaque configuration.  
  
2.  Cliquez sur l'onglet **OLE Types** et spécifiez un nom de fichier dans le champ de nom de fichier de **Output header**.  Utilisez un nom de fichier qui n'est pas déjà utilisé par votre projet, car MkTypLib remplacera un fichier déjà existant.  Cliquez sur **OK** pour fermer la boîte de dialogue **Paramètres de version**.  
  
 Pour ajouter à votre projet les définitions de **UUID** du fichier d'en\-tête généré par MkTypLib:  
  
1.  Inclut le fichier d'en\-tête généré par MkTypLib dans le standard inclut le fichier d'en\-tête, STDAFX.H.  
  
2.  Créez un nouveau fichier, INITIIDS.CPP, et ajoutez le à votre projet.  Dans ce fichier, incluez le fichier d'en\-tête généré par MkTypLib après avoir inclus OLE2.H et INITGUID.H :  
  
    ```  
    // initIIDs.c: defines IIDs for dual interfaces  
    // This must not be built with precompiled header.  
      #include <ole2.h>  
      #include <initguid.h>  
      #include "acdual.h"  
    ```  
  
3.  Dans le menu **Version**, cliquez sur **Paramètres**, puis sélectionnez le fichier INITIIDS.CPP dans la liste des fichiers à chaque configuration.  
  
4.  Cliquez sur l'onglet de **C\+\+**, cliquez sur la catégorie **En\-têtes précompilés**, puis sélectionnez la case d'option de **Non utilisation d'en\-têtes compilés**.  Cliquez sur OK pour fermer la boîte de dialogue **Paramètres de version**.  
  
## spécification du nom de classe d'objets correct dans une bibliothèque de types ;  
 Les assistants fournis avec Visual C\+\+ utilisent incorrectement le nom de classe d'implémentation pour spécifier la coclasse dans le fichier d'ODL de serveur pour les classes créable par OLE.  Si cette opération fonctionne, le nom de classe d'implémentation n'est probablement pas le nom de classe que vous souhaitez que les utilisateurs de votre objet utilisent.  Pour spécifier le bon nom, ouvrez le fichier d'ODL, recherchez chaque instruction de la coclasse, et remplacer le nom de classe d'implémentation par le nom externe correct.  
  
 Notez que lorsque l'instruction de la coclasse est modifiée, les noms de variables de **CLSID**s dans le fichier d'en\-tête généré par MkTypLib changeront en conséquence.  Vous devez mettre à jour votre code afin d'utiliser les nouveaux noms de variables.  
  
## gestion des Exceptions et des interfaces d'erreur Automation.  
 Les méthodes de votre objet automation et les fonctions d'accesseurs de propriété peuvent lever des exceptions.  Dans ce cas, vous devez les traiter dans l'implémentation de l'interface double et passer les informations relatives à l'exception au contrôleur à travers l'interface de gestion des erreurs OLE Automation, **IErrorInfo**.  Cette interface fournit des informations d'erreur détaillées et contextuelles à travers à la fois de `IDispatch` et des interfaces de VTBL.  Pour indiquer qu'un gestionnaire d'erreurs est disponible, vous devez implémenter l'interface **ISupportErrorInfo**.  
  
 Pour illustrer le mécanisme de gestion des erreurs, supposez que les fonctions générées par ClassWizard utilisées pour implémenter les exceptions standard supportent les lancers d'exceptions.  L'implémentation par MFC de **IDispatch::Invoke** intercepte généralement les exceptions et les convertit en une structure d'EXCEPTINFO qui est retournée via l'appel de `Invoke`.  Toutefois, lorsque l'interface de VTBL est utilisée, vous êtes chargé d'intercepter les exceptions vous\-même.  Comme exemple de protection des méthodes de l'interface double :  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)  
{  
   METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
   TRY_DUAL(IID_IDualAClick)  
   {  
      // MFC automatically converts from Unicode BSTR to   
      // Ansi CString, if necessary...  
      pThis->m_str = newText;  
      return NOERROR;  
   }  
   CATCH_ALL_DUAL  
}  
```  
  
 `CATCH_ALL_DUAL` prend soin de retourner un code d'erreur approprié lorsqu'une exception se produit.  `CATCH_ALL_DUAL` convertit une exception de MFC en des informations de gestion des erreurs de OLE Automation via l'interface **ICreateErrorInfo**. \(Une macro de `CATCH_ALL_DUAL` d'exemple se situe dans le fichier MFCDUAL.H dans l'essai de [ACDUAL](../top/visual-cpp-samples.md).  La fonction qu'elle utilise pour gérer les exceptions, `DualHandleException`, se trouve dans le fichier MFCDUAL.CPP.\) `CATCH_ALL_DUAL` détermine le code d'erreur à retourner en fonction du type d'exception qui s'est produite :  
  
-   –[COleDispatchException](../mfc/reference/coledispatchexception-class.md) dans ce cas, `HRESULT` est construit à l'aide du code suivant :  
  
    ```  
    hr = MAKE_HRESULT(SEVERITY_ERROR, FACILITY_ITF,   
                               (e->m_wCode + 0x200));  
    ```  
  
     Cela crée un `HRESULT` spécifique à l'interface qui a provoqué l'exception.  Le code d'erreur est décalé par 0x200 pour éviter tout conflit avec le `HRESULT`défini par le système s des interfaces OLE standard.  
  
-   –[CMemoryException](../mfc/reference/cmemoryexception-class.md) dans ce cas, `E_OUTOFMEMORY` est retourné.  
  
-   Toute autre exception \(dans ce cas, `E_UNEXPECTED` est retournée.  
  
 Pour indiquer que le gestionnaire d'erreurs OLE Automation est utilisé, vous devez également implémenter l'interface de **ISupportErrorInfo**.  
  
 D'abord, ajouter du code à votre définition de classe d'automation pour indiquer qu'elle prend en charge **ISupportErrorInfo**.  
  
 Ensuite, ajoutez le code au mappage d'interface de la classe d'automation pour associer la classe d'implémentation de **ISupportErrorInfo** avec le mécanisme de `QueryInterface` de MFC.  Le relevé `INTERFACE_PART` correspond à la classe définie pour **ISupportErrorInfo**.  
  
 Enfin, implémentez la classe définie pour prendre en charge **ISupportErrorInfo**.  
  
 \(L'exemple de [ACDUAL](../top/visual-cpp-samples.md) contient trois macros aidant à effectuer ces trois étapes, `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, et `IMPLEMENT_DUAL_ERRORINFO`, tout contenu dans MFCDUAL.H.\)  
  
 L'exemple suivant implémente une classe définie pour prendre en charge **ISupportErrorInfo**.  `CAutoClickDoc` est le nom de votre classe automation et `IID_IDualAClick` est le **IID** de l'interface qui est la source des erreurs signalées par le biais de l'objet d'erreur OLE Automation :  
  
```  
STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::AddRef()   
{  
   METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
   return pThis->ExternalAddRef();   
}   
STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::Release()   
{   
   METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
   return pThis->ExternalRelease();   
}   
STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::QueryInterface(   
   REFIID iid, LPVOID* ppvObj)   
{   
   METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
   return pThis->ExternalQueryInterface(&iid, ppvObj);   
}   
STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::InterfaceSupportsErrorInfo(   
   REFIID iid)   
{   
   METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
   return (iid == IID_IDualAClick) ? S_OK : S_FALSE;   
}  
```  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)
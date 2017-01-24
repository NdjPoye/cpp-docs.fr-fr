---
title: "TN038&#160;: impl&#233;mentation IUnknown MFC/OLE | Microsoft Docs"
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
  - "macros d'agrégation (C++)"
  - "BEGIN_INTERFACE_MAP (macro)"
  - "BEGIN_INTERFACE_PART (macro)"
  - "interfaces COM, interface de base"
  - "DECLARE_INTERFACE_MAP (macro)"
  - "END_INTERFACE_MAP (macro)"
  - "END_INTERFACE_PART (macro)"
  - "INTERFACE_PART (macro)"
  - "Interface IUnknown"
  - "METHOD_PROLOGUE (macro)"
  - "OLE (C++), implémenter l'interface IUnknown"
  - "STDMETHOD (macro)"
  - "TN038"
ms.assetid: 19d946ba-beaf-4881-85c6-0b598d7f6f11
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN038&#160;: impl&#233;mentation IUnknown MFC/OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Au cœur d'OLE 2 se trouve COM ou « OLE Component Object Model ».  COM définit une norme de communication entre les objets coopérants.  Cela inclut les détails de présentation d'un « objet », notamment le mode de distribution des méthodes sur un objet.  COM définit aussi une classe de base dont sont dérivées toutes les classes compatibles COM.  Cette classe de base est [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  Bien que l'interface [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) soit considérée comme une classe C\+\+, COM ne se limite pas un langage précis. Il peut être implémenté en C, PASCAL ou tout autre langage prenant en charge la structure binaire d'un objet COM.  
  
 OLE fait référence à toutes les classes dérivées de [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) sous forme d'« interfaces ». Il s'agit d'une distinction importante, car une « interface » telle que [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) ne s'accompagne d'aucune implémentation.  Elle définit simplement le protocole de communication utilisé par les objets et non les détails de cette implémentation.  Cela est raisonnable pour un système qui prévoit une flexibilité maximale.  MFC a pour fonction d'implémenter un comportement par défaut pour les programmes MFC\/C\+\+.  
  
 Pour comprendre l'implémentation MFC de l'interface [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), vous devez d'abord en comprendre les caractéristiques.  Une version simplifiée de l'interface [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) est définie ci\-dessous :  
  
```  
class IUnknown  
{  
public:  
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj) = 0;  
    virtual ULONG AddRef() = 0;  
    virtual ULONG Release() = 0;  
};  
```  
  
> [!NOTE]
>  Certains détails nécessaires de la convention d'appel, tels que `__stdcall`, sont omis dans cette illustration.  
  
 Les fonctions membres [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) et [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) contrôlent la gestion de mémoire de l'objet.  COM utilise un système de comptage de références pour assurer le suivi des objets.  Les objets ne sont jamais référencés directement comme en C\+\+.  Au lieu de cela, les objets COM sont toujours référencés au moyen d'un pointeur.  Pour libérer l'objet une fois que le propriétaire a fini de l'utiliser, il convient d'appeler le membre [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) de l'objet \(au contraire d'un objet C\+\+ traditionnel, qui aurait nécessité l'utilisation de l'opérateur delete\).  Le mécanisme de comptage de références autorise la gestion de plusieurs références à un même objet.  Une implémentation d'[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) et de [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) assure un comptage des références sur l'objet \(l'objet n'est pas supprimé tant que son décompte de références n'est pas égal à zéro\).  
  
 [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) et [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) sont assez simples du point de vue de l'implémentation.  Voici une implémentation rudimentaire :  
  
```  
ULONG CMyObj::AddRef()   
{   
    return ++m_dwRef;   
}  
  
ULONG CMyObj::Release()   
{   
    if (--m_dwRef == 0)   
    {  
        delete this;   
        return 0;  
    }  
    return m_dwRef;  
}  
```  
  
 La fonction membre [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) est un peu plus intéressante.  Un objet dont les seules fonctions membres sont [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) et [version](http://msdn.microsoft.com/library/windows/desktop/ms682317) n'a que peu d'intérêt. Il serait utile de demander à l'objet de remplir plus de fonctions que l'interface [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) ne peut en assurer.  C'est ici que l'intérêt de la fonction [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) prend tout son sens.  Elle vous permet d'obtenir une « interface » différente sur le même objet.  Ces interfaces sont généralement dérivées d'[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) et ajoutent des fonctionnalités supplémentaires avec l'addition de nouvelles fonctions membres.  Les interfaces COM ne font jamais déclarer de variables membres dans l'interface, et toutes les fonctions membres sont déclarées de façon purement virtuelle.  Par exemple :  
  
```  
class IPrintInterface : public IUnknown  
{  
public:  
    virtual void PrintObject() = 0;  
};  
```  
  
 Pour obtenir une interface IPrintInterface dans le cas où vous ne disposez que d'une interface [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), appelez [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) en utilisant l'`IID` de l'interface **IPrintInterface**.  Un `IID` est un nombre 128 bits qui identifie l'interface de manière unique.  À chaque interface définie par vous\-même ou par OLE correspond un `IID`.  Si `pUnk` est un pointeur vers un objet [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), voici à quoi peut ressembler le code permettant de récupérer une interface IPrintInterface :  
  
```  
IPrintInterface* pPrint = NULL;  
if (pUnk->QueryInterface(IID_IPrintInterface,   
    (void**)&pPrint) == NOERROR)  
{  
    pPrint->PrintObject();  
    pPrint->Release();     
        // release pointer obtained via QueryInterface  
}  
```  
  
 Cela paraît assez simple, mais comment implémenteriez\-vous un objet qui prenne en charge à la fois IPrintInterface et l'interface [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) ?  Dans ce cas, c'est simple dans la mesure où IPrintInterface est directement dérivé d'[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) \(l'implémentation d'IPrintInterface assure une prise en charge automatique d'[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)\).  Exemple :  
  
```  
class CPrintObj : public CPrintInterface  
{  
    virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);  
    virtual ULONG AddRef();  
    virtual ULONG Release();  
    virtual void PrintObject();  
};  
```  
  
 Les implémentations d'[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) et de [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) serait parfaitement identiques aux implémentations précédentes.  **CPrintObj::QueryInterface** se présenterait ainsi :  
  
```  
HRESULT CPrintObj::QueryInterface(REFIID iid, void FAR* FAR* ppvObj)  
{  
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)  
    {  
        *ppvObj = this;  
        AddRef();  
        return NOERROR;  
    }  
    return E_NOINTERFACE;  
}  
```  
  
 Comme vous pouvez le constater, si l'identificateur d'interface \(IID\) est reconnu, un pointeur est retourné vers l'objet ; sinon, une erreur se produit.  Notez aussi qu'une interface [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) aboutie produit un [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) implicite.  Bien entendu, vous devrez aussi implémenter CEditObj::Print.  C'est simple dans la mesure où l'interface IPrintInterface a été directement dérivée de l'interface [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  Cependant, si vous voulez prendre en charge deux interfaces différentes, toutes deux dérivées de l'interface [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), tenez compte des points suivants :  
  
```  
class IEditInterface : public IUnkown  
{  
public:  
    virtual void EditObject() = 0;  
};  
```  
  
 Bien qu'il existe plusieurs façons d'implémenter une classe prenant en charge à la fois IEditInterface et IPrintInterface, notamment en utilisant l'héritage multiple C\+\+, cette note se concentrera sur l'utilisation de classes imbriquées pour l'implémentation de cette fonctionnalité.  
  
```  
class CEditPrintObj  
{  
public:  
    CEditPrintObj();  
  
    HRESULT QueryInterface(REFIID iid, void**);  
    ULONG AddRef();  
    ULONG Release();  
    DWORD m_dwRef;  
  
    class CPrintObj : public IPrintInterface  
    {  
    public:  
        CEditPrintObj* m_pParent;  
        virtual HRESULT QueryInterface(REFIID iid, void** ppvObj);  
        virtual ULONG AddRef();  
        virtual ULONG Release();  
    } m_printObj;  
  
    class CEditObj : public IEditInterface  
    {  
    public:  
        CEditPrintObj* m_pParent;  
        virtual ULONG QueryInterface(REFIID iid, void** ppvObj);  
        virtual ULONG AddRef();  
        virtual ULONG Release();  
    } m_editObj;  
};  
```  
  
 L'intégralité de l'implémentation est incluse ci\-dessous :  
  
```  
CEditPrintObj::CEditPrintObj()  
{  
    m_editObj.m_pParent = this;  
    m_printObj.m_pParent = this;  
}  
  
ULONG CEditPrintObj::AddRef()   
{   
    return ++m_dwRef;  
}  
  
CEditPrintObj::Release()  
{  
    if (--m_dwRef == 0)  
    {  
        delete this;  
        return 0;  
    }  
    return m_dwRef;  
}  
  
HRESULT CEditPrintObj::QueryInterface(REFIID iid, void** ppvObj)  
{  
    if (iid == IID_IUnknown || iid == IID_IPrintInterface)  
    {  
        *ppvObj = &m_printObj;  
        AddRef();  
        return NOERROR;  
    }  
    else if (iid == IID_IEditInterface)  
    {  
        *ppvObj = &m_editObj;  
        AddRef();  
        return NOERROR;  
    }  
    return E_NOINTERFACE;  
}  
  
ULONG CEditPrintObj::CEditObj::AddRef()   
{   
    return m_pParent->AddRef();   
}  
  
ULONG CEditPrintObj::CEditObj::Release()   
{   
    return m_pParent->Release();   
}  
  
HRESULT CEditPrintObj::CEditObj::QueryInterface(  
    REFIID iid, void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid, ppvObj);   
}  
  
ULONG CEditPrintObj::CPrintObj::AddRef()   
{   
    return m_pParent->AddRef();   
}  
  
ULONG CEditPrintObj::CPrintObj::Release()   
{   
    return m_pParent->Release();   
}  
  
HRESULT CEditPrintObj::CPrintObj::QueryInterface(  
    REFIID iid, void** ppvObj)   
{   
    return m_pParent->QueryInterface(iid, ppvObj);   
}  
```  
  
 Plutôt que de dupliquer le code dans CEditPrintObj::CEditObj et CEditPrintObj::CPrintObj, notez que la majeure partie de l'implémentation d'[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) est placée dans la classe CEditPrintObj.  Cela réduit la quantité de code et évite les bogues.  Le point essentiel ici est qu'il est possible d'appeler [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) à partir de l'interface IUnknown de façon à récupérer n'importe quelle interface prise en charge par l'objet, et il est possible d'en faire autant à partir de chacune de ces interfaces.  Cela signifie que toutes les fonctions [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) disponible dans chaque interface doivent se comportent exactement de la même manière.  Pour que ces objets incorporés appellent l'implémentation dans l'« objet externe », un pointeur arrière est utilisée \(m\_pParent\).  Le pointeur m\_pParent est initialisé dans le cadre du constructeur CEditPrintObj.  Vous devez ensuite implémenter CEditPrintObj::CPrintObj::PrintObject, ainsi que CEditPrintObj::CEditObj::EditObject.  Une certaine quantité de code a été ajoutée pour adjoindre une fonctionnalité permettant de modifier l'objet.  Heureusement, il est assez rare que les interfaces aient une seule fonction membre \(quoique cela puisse arriver\). Dans ce cas, EditObject et PrintObject sont généralement combinés dans une interface unique.  
  
 Cela représente beaucoup d'explications et beaucoup de code pour un scénario aussi simple.  Les classes MFC\/OLE offrent une alternative plus simple.  L'implémentation MFC utilise une technique similaire à la façon dont Windows inclut les messages dans un wrapper avec les tables des messages.  Cette fonctionnalité est appelée *Tables d'interface* et est décrite dans la section suivante.  
  
## Tables d'interface MFC  
 MFC\/OLE inclut une implémentation de « Tables d'interface » qui s'apparente aux « Tables des messages » et aux « Tables de dispatch » de MFC sur le plan du concept et de l'exécution.  Les principales fonctionnalités des Tables d'interface de MFC sont les suivantes :  
  
-   Une implémentation standard d'[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), intégrée à la classe `CCmdTarget`.  
  
-   Gestion du nombre de références, modifié par [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) et [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317).  
  
-   Implémentation de [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) pilotée par les données.  
  
 Par ailleurs, les tables d'interface prennent en charge les fonctionnalités avancées suivantes :  
  
-   Prise en charge de la création d'objets COM agrégeables.  
  
-   Prise en charge de l'utilisation d'objets d'agrégation dans l'implémentation d'un objet COM.  
  
-   L'implémentation est hookable et extensible.  
  
 Pour plus d'informations sur l'agrégation, consultez la rubrique [Agrégation](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx).  
  
 La prise en charge des tables d'interface de MFC est ancrée dans la classe `CCmdTarget`.  `CCmdTarget` « *intègre* » un nombre de références, ainsi que toutes les fonctions membres associées à l'implémentation d'[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) \(par exemple, le nombre de références se trouve dans `CCmdTarget`\).  Pour créer une classe qui prenne en charge OLE COM, vous devez faire dériver une classe de `CCmdTarget` et utiliser diverses macros, ainsi que des fonctions membres de `CCmdTarget` pour implémenter les interfaces souhaitées.  L'implémentation de MFC utilise des classes imbriquées pour définir chaque implémentation d'interface de façon très similaire à l'exemple ci\-dessus.  Cela est facilité par une implémentation standard de l'interface IUnknown et par un certain nombre de macros qui permettent d'éliminer une partie du code répétitif.  
  
## Principes fondamentaux des tables d'interface  
  
#### Pour implémenter une classe en utilisant des tables d'interface de MFC  
  
1.  Faites dériver une classe directement ou indirectement de `CCmdTarget`.  
  
2.  Utilisez la fonction `DECLARE_INTERFACE_MAP` dans la définition de la classe dérivée.  
  
3.  Pour chaque interface que vous voulez prendre en charge, utilisez les macros `BEGIN_INTERFACE_PART` et `END_INTERFACE_PART` dans la définition de la classe.  
  
4.  Dans le fichier d'implémentation, utilisez les macros `BEGIN_INTERFACE_MAP` et `END_INTERFACE_MAP` pour définir la table d'interface de la classe.  
  
5.  Pour chaque IID pris en charge, utilisez la macro `INTERFACE_PART` entre les macros `BEGIN_INTERFACE_MAP` et `END_INTERFACE_MAP` pour mapper cet IID à une « partie » spécifique de votre classe.  
  
6.  Implémentez chacune des classes imbriquées qui représentent les interfaces que vous prenez en charge.  
  
7.  Utilisez la macro `METHOD_PROLOGUE` pour accéder au parent, objet dérivé de `CCmdTarget`.  
  
8.  [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) et [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) peuvent déléguer à `CCmdTarget` l'implémentation de ces fonctions \(`ExternalAddRef`, `ExternalRelease` et `ExternalQueryInterface`\).  
  
 L'exemple CPrintEditObj ci\-dessus aurait pu être implémenté comme suit :  
  
```  
class CPrintEditObj : public CCmdTarget  
{  
public:  
    // member data and member functions for CPrintEditObj go here  
  
// Interface Maps  
protected:  
    DECLARE_INTERFACE_MAP()  
  
    BEGIN_INTERFACE_PART(EditObj, IEditInterface)  
        STDMETHOD_(void, EditObject)();  
    END_INTERFACE_PART(EditObj)  
  
    BEGIN_INTERFACE_PART(PrintObj, IPrintInterface)  
        STDMETHOD_(void, PrintObject)();  
    END_INTERFACE_PART(PrintObj)  
};  
```  
  
 La déclaration ci\-dessus crée une classe dérivée de `CCmdTarget`.  La macro `DECLARE_INTERFACE_MAP` indique à l'infrastructure que cette classe aura une table d'interface personnalisée.  De plus, les macros `BEGIN_INTERFACE_PART` et `END_INTERFACE_PART` définissent des classes imbriquées, dans ce cas avec les noms CEditObj et CPrintObj \(le X sert seulement à différencier les classes imbriquées des classes globales qui commencent par « C » et des classes d'interface qui commencent par « I »\).  Deux membres imbriqués de ces classes sont créés : m\_CEditObj et m\_CPrintObj, respectivement.  Les macros déclarent automatiquement les fonctions [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) et [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) ; par conséquent, vous ne déclarez que les fonctions propres à cette interface : EditObject et PrintObject \(la macro OLE `STDMETHOD` est utilisée pour que `_stdcall` et les mots clés virtuels soient fournis en fonction de la plateforme cible\).  
  
 Pour implémenter la table d'interface pour cette classe :  
  
```  
BEGIN_INTERFACE_MAP(CPrintEditObj, CCmdTarget)  
    INTERFACE_PART(CPrintEditObj, IID_IPrintInterface, PrintObj)  
    INTERFACE_PART(CPrintEditObj, IID_IEditInterface, EditObj)  
END_INTERFACE_MAP()  
```  
  
 Cela a pour effet de connecter l'IID d'IID\_IPrintInterface à m\_CPrintObj et IID\_IEditInterface à m\_CEditObj, respectivement.  L'implémentation `CCmdTarget` de [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) \(`CCmdTarget::ExternalQueryInterface`\) utilise cette table pour retourner des pointeurs vers m\_CPrintObj et m\_CEditObj quand cela est demandé.  Il n'est pas nécessaire d'inclure une entrée pour `IID_IUnknown` ; l'infrastructure utilisera la première interface de la table \(en l'occurrence, m\_CPrintObj\) quand `IID_IUnknown` sera demandé.  
  
 Même si la macro `BEGIN_INTERFACE_PART` a déclaré automatiquement les fonctions [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) et [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521), vous devez quand même les implémenter :  
  
```  
ULONG FAR EXPORT CEditPrintObj::XEditObj::AddRef()  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    return pThis->ExternalAddRef();  
}  
  
ULONG FAR EXPORT CEditPrintObj::XEditObj::Release()  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    return pThis->ExternalRelease();  
}  
  
HRESULT FAR EXPORT CEditPrintObj::XEditObj::QueryInterface(  
    REFIID iid, void FAR* FAR* ppvObj)  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    return (HRESULT)pThis->ExternalQueryInterface(&iid, ppvObj);  
}  
  
void FAR EXPORT CEditPrintObj::XEditObj::EditObject()  
{  
    METHOD_PROLOGUE(CEditPrintObj, EditObj)  
    // code to "Edit" the object, whatever that means...  
}  
```  
  
 L'implémentation pour CEditPrintObj::CPrintObj serait similaire aux définitions ci\-dessus de CEditPrintObj::CEditObj.  Bien qu'il soit possible de créer une macro qui permettrait de générer automatiquement ces fonctions \(comme c'était le cas à un stade plus précoce du développement de MFC\/OLE\), il devient difficile de définir des points d'arrêt quand une macro génère plus d'une ligne de code.  C'est pour cette raison que ce code est développé manuellement.  
  
 En utilisant l'implémentation des tables des messages de l'infrastructure, il y a un certain nombre de choses qu'il n'était pas nécessaire de faire :  
  
-   implémenter QueryInterface,  
  
-   implémenter AddRef et Release,  
  
-   déclarer l'une ou l'autre de ces méthodes intégrées dans les deux interfaces.  
  
 Par ailleurs, l'infrastructure utilise des tables des messages en interne.  Vous pouvez ainsi dériver d'une classe d'infrastructure, disons `COleServerDoc`, qui prend déjà en charge certaines interfaces et fournit des remplacements ou des ajouts aux interfaces fournies par l'infrastructure.  Si cela est possible, c'est parce que l'infrastructure prend entièrement en charge l'héritage d'une table d'interface à partir d'une classe de base.  C'est la raison pour laquelle `BEGIN_INTERFACE_MAP` prend comme deuxième paramètre le nom de la classe de base.  
  
> [!NOTE]
>  En général, il n'est pas possible de réutiliser les implémentations intégrées des interfaces OLE de MFC en héritant simplement de la spécialisation incorporée de ces interfaces de la version MFC.  Cela n'est pas possible, car l'utilisation de la macro `METHOD_PROLOGUE` en vue d'accéder à l'objet contenant dérivé de `CCmdTarget` implique un *décalage fixe* de l'objet incorporé par rapport à l'objet dérivé de `CCmdTarget`.  Cela signifie, par exemple, que vous ne pouvez pas faire dériver un XMyAdviseSink incorporé de l'implémentation MFC dans `COleClientItem::XAdviseSink`, car XAdviseSink s'attend à un certain décalage entre sa position et le sommet de l'objet `COleClientItem`.  
  
> [!NOTE]
>  Vous pouvez cependant déléguer à l'implémentation MFC pour toutes les fonctions qui doivent constituer le comportement par défaut de MFC.  Cette opération est effectuée dans l'implémentation MFC d'`IOleInPlaceFrame` \(XOleInPlaceFrame\) dans la classe `COleFrameHook` \(elle délègue à m\_xOleInPlaceUIWindow pour de nombreuses fonctions\).  Cette conception a été choisie pour réduire, au moment de l'exécution, la taille des objets qui implémentent de nombreuses interfaces ; elle évite de recourir à un pointeur de retour \(à la manière dont était utilisée la méthode m\_pParent dans la section précédente\).  
  
### Agrégation et tables d'interface  
 En plus de prendre en charge les objets COM autonomes, MFC prend aussi en charge l'agrégation.  L'agrégation proprement dite est un sujet trop complexe pour être abordé ici ; pour plus d'informations sur l'agrégation, consultez la rubrique [Agrégation](http://msdn.microsoft.com/library/windows/desktop/ms686558\(v=vs.85\).aspx).  Dans cette note, nous nous bornerons à décrire la prise en charge de l'agrégation intégrée à l'infrastructure et aux tables d'interface.  
  
 Il existe deux façons d'utiliser l'agrégation : soit en utilisant un objet COM qui prenne en charge l'agrégation, soit en implémentant un objet qui puisse être agrégé par un autre.  Autrement dit, cela consiste à « utiliser un objet d'agrégation » et à « rendre un objet agrégeable ».  MFC prend en charge les deux méthodes.  
  
### Utilisation d'un objet d'agrégation  
 Pour utiliser un objet d'agrégation, il doit exister un moyen de lier l'agrégation au mécanisme QueryInterface.  En d'autres termes, l'objet d'agrégation doit se comporter comme s'il s'agissait d'une part native de votre objet.  La question est de savoir comment il se lie au mécanisme de table d'interface de MFC ?  En plus de la macro `INTERFACE_PART`, où un objet imbriqué est mappé à un IID, vous pouvez aussi déclarer d'un objet d'agrégation dans le cadre de votre classe dérivée `CCmdTarget`.  Pour cela, vous devez utiliser la macro `INTERFACE_AGGREGATE`.  Elle vous permet de spécifier une variable membre \(qui doit être un pointeur désignant une interface [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) ou une classe dérivée\), qui doit être intégrée au mécanisme de table d'interface.  Si le pointeur n'a pas la valeur NULL quand `CCmdTarget::ExternalQueryInterface` est appelé, l'infrastructure appelle automatiquement la fonction membre [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) de l'objet d'agrégation, dans la mesure où l'`IID` demandé n'est pas l'un des `IID` natifs pris en charge par l'objet `CCmdTarget` lui\-même.  
  
##### Pour utiliser la macro INTERFACE\_AGGREGATE  
  
1.  Déclarez une variable membre \(une interface `IUnknown*`\) qui contiendra un pointeur vers l'objet d'agrégation.  
  
2.  Incluez une macro `INTERFACE_AGGREGATE` macro dans votre table d'interface, qui fait référence à la variable de membre par son nom.  
  
3.  À un moment donné \(généralement dans le cadre de `CCmdTarget::OnCreateAggregates`\), initialisez la variable membre avec une valeur différente de NULL.  
  
 Exemple :  
  
```  
class CAggrExample : public CCmdTarget  
{  
public:  
    CAggrExample();  
  
protected:  
    LPUNKNOWN m_lpAggrInner;  
    virtual BOOL OnCreateAggregates();  
  
    DECLARE_INTERFACE_MAP()  
    // "native" interface part macros may be used here  
};  
  
CAggrExample::CAggrExample()  
{  
    m_lpAggrInner = NULL;  
}  
  
BOOL CAggrExample::OnCreateAggregates()  
{  
    // wire up aggregate with correct controlling unknown  
    m_lpAggrInner = CoCreateInstance(CLSID_Example,  
        GetControllingUnknown(), CLSCTX_INPROC_SERVER,  
        IID_IUnknown, (LPVOID*)&m_lpAggrInner);  
    if (m_lpAggrInner == NULL)  
        return FALSE;  
    // optionally, create other aggregate objects here  
    return TRUE;  
}  
  
BEGIN_INTERFACE_MAP(CAggrExample, CCmdTarget)  
    // native "INTERFACE_PART" entries go here  
    INTERFACE_AGGREGATE(CAggrExample, m_lpAggrInner)  
END_INTERFACE_MAP()  
```  
  
 La variable m\_lpAggrInner est initialisée dans le constructeur avec la valeur NULL.  L'infrastructure ne tient pas compte de la présence d'une variable membre NULL dans l'implémentation par défaut de [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  `OnCreateAggregates` offre un moyen efficace de créer véritablement vos objets d'agrégation.  Vous devrez l'appeler explicitement si vous créez l'objet en dehors de l'implémentation MFC de `COleObjectFactory`.  L'intérêt de créer des agrégations dans `CCmdTarget::OnCreateAggregates` et d'utiliser `CCmdTarget::GetControllingUnknown` vous apparaîtra évident quand nous aborderons la question de la création d'objets agrégeables.  
  
 Cette technique mettre à la disposition de votre objet toutes les interfaces prises en charge par l'objet d'agrégation, ainsi que ses interfaces natives.  Si vous voulez seulement un sous\-ensemble des interfaces prises en charge par l'agrégation, vous pouvez substituer `CCmdTarget::GetInterfaceHook`.  Vous disposez alors d'une faible capacité de hook, à l'instar de [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  Habituellement, les utilisateurs choisissent toutes les interfaces prises en charge par l'agrégation.  
  
### Rendre une implémentation d'objet agrégeable  
 Pour qu'un objet soit agrégeable, l'implémentation d'[AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), de [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) et de [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) doit déléguer à un « inconnu de contrôle ». En d'autres termes, pour faire partie de l'objet, elle doit déléguer [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) et [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) à un autre objet, également dérivé d'[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  Cet « inconnu de contrôle » est fourni à l'objet au moment où il est créé. Autrement dit, il est fourni à l'implémentation de `COleObjectFactory`.  Dans la mesure où cette implémentation s'accompagne de quelques frais généraux, ce qui n'est pas souhaitable dans certains cas, MFC en fait une option.  Pour rendre un objet agrégeable, vous devez appeler `CCmdTarget::EnableAggregation` à partir du constructeur de l'objet.  
  
 Si l'objet utilise également des agrégations, vous devez aussi veiller à passer le bon « inconnu de contrôle » aux objets d'agrégation.  En général, ce pointeur [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) est passé à l'objet au moment où l'agrégation est créée.  Par exemple, le paramètre pUnkOuter est l'« inconnu de contrôle » pour les objets créés avec `CoCreateInstance`.  Le pointeur « inconnu de contrôle » adéquat peut être récupéré en appelant `CCmdTarget::GetControllingUnknown`.  Cependant, la valeur retournée par cette fonction n'est pas valide dans le cadre du constructeur.  C'est pourquoi il est conseillé de créer ses agrégations uniquement dans le cadre d'une substitution de `CCmdTarget::OnCreateAggregates`, où la valeur de retour de `GetControllingUnknown` est fiable, même si elle a été créée à partir de l'implémentation de `COleObjectFactory`.  
  
 De même, il est important que l'objet manipule le nombre de références approprié lors de l'ajout ou de la libération de nombres de références artificiels.  Pour vous assurer que c'est le cas, appelez toujours `ExternalAddRef` et `ExternalRelease` au lieu de `InternalRelease` et `InternalAddRef`.  Il est rare d'appeler `InternalRelease` ou `InternalAddRef` sur une classe qui prend en charge l'agrégation.  
  
### Documents de référence  
 L'utilisation avancée d'OLE, qui consiste notamment à définir vos propres interfaces ou à substituer l'implémentation par l'infrastructure des interfaces OLE, nécessite l'utilisation du mécanisme de table d'interface sous\-jacent.  
  
 Cette section décrit chaque macro, ainsi que les API utilisées pour implémenter ces fonctionnalités avancées.  
  
### Description de la fonction CCmdTarget::EnableAggregation  
  
```  
  
void EnableAggregation();  
```  
  
## Notes  
 Appelez cette fonction dans le constructeur de la classe dérivée si vous souhaitez prendre en charge l'agrégation OLE pour les objets de ce type.  Elle prépare une implémentation spéciale d'IUnknown qui est nécessaire aux objets agrégeables.  
  
### Description de la fonction CCmdTarget::ExternalQueryInterface  
  
```  
  
              DWORD ExternalQueryInterface(    const void FAR* lpIID,    LPVOID FAR* ppvObj   
);  
```  
  
## Notes  
  
#### Paramètres  
 `lpIID`  
 Pointeur lointain vers un IID \(premier argument à destination de QueryInterface\)  
  
 `ppvObj`  
 Pointeur vers une interface IUnknown\* \(deuxième argument à destination de QueryInterface\)  
  
## Notes  
 Appelez cette fonction dans votre implémentation d'IUnknown pour chaque interface que votre classe implémente.  Cette fonction assure l'implémentation standard pilotée par des données de QueryInterface en s'appuyant sur la table d'interface de votre objet.  Il est nécessaire d'effectuer une conversation de type \(transtypage\) de la valeur de retour en HRESULT.  Si l'objet est agrégée, cette fonction appelle l'« IUnknown de contrôle » au lieu d'utiliser la table d'interface locale.  
  
### Description de la fonction CCmdTarget::ExternalAddRef  
  
```  
  
DWORD ExternalAddRef();  
```  
  
## Notes  
 Appelez cette fonction dans votre implémentation d'IUnknown::AddRef pour chaque interface que votre classe implémente.  La valeur de retour est le nouveau nombre de références au niveau de l'objet CCmdTarget.  Si l'objet est agrégée, cette fonction appelle l'« IUnknown de contrôle » au lieu de manipuler le nombre de références locales.  
  
### Description de la fonction CCmdTarget::ExternalRelease  
  
```  
  
DWORD ExternalRelease();  
  
```  
  
## Notes  
 Appelez cette fonction dans votre implémentation d'IUnknown::Release pour chaque interface que votre classe implémente.  La valeur de retour indique le nouveau nombre de références au niveau de l'objet.  Si l'objet est agrégée, cette fonction appelle l'« IUnknown de contrôle » au lieu de manipuler le nombre de références locales.  
  
### Description de la macro DECLARE\_INTERFACE\_MAP  
  
```  
  
DECLARE_INTERFACE_MAP  
  
```  
  
## Notes  
 Utilisez cette macro dans une classe dérivée de `CCmdTarget` qui sera dotée d'une table d'interface.  Elle s'utilise à peu près de la même façon que `DECLARE_MESSAGE_MAP`.  L'appel de cette macro doit être placé dans la définition de la classe, généralement dans un fichier d'en\-tête \(.H\).  Une classe contenant `DECLARE_INTERFACE_MAP` doit définir la table d'interface dans le fichier d'implémentation \(.CPP\) à l'aide des macros `BEGIN_INTERFACE_MAP` et `END_INTERFACE_MAP`.  
  
### Description des macros BEGIN\_INTERFACE\_PART et END\_INTERFACE\_PART  
  
```  
  
              BEGIN_INTERFACE_PART(   
   localClass,  
   iface   
);  
END_INTERFACE_PART(   
   localClass   
)  
```  
  
## Notes  
  
#### Paramètres  
 l`ocalClass`  
 Nom de la classe qui implémente l'interface  
  
 `iface`  
 Nom de l'interface que cette classe implémente  
  
## Notes  
 Pour chaque interface que votre classe doit implémenter, vous devez disposer d'une paire `BEGIN_INTERFACE_PART` et `END_INTERFACE_PART`.  Ces macros définissent une classe locale dérivée de l'interface OLE que vous définissez, ainsi qu'une variable membre incorporée de cette classe.  Les membres [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379), [Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) et [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521) sont déclarés automatiquement.  Vous devez inclure les déclarations des autres fonctions membres qui font partie de l'interface implémentée \(ces déclarations sont placées entre les macros `BEGIN_INTERFACE_PART` et `END_INTERFACE_PART`\).  
  
 L'argument `iface` est l'interface OLE que vous souhaitez implémenter, par exemple, `IAdviseSink` ou `IPersistStorage` \(voire votre propre interface personnalisée\).  
  
 L'argument `localClass` est le nom de la classe locale qui sera définie.  Un « X » est automatiquement ajouté au nom.  L'emploi de cette convention d'affectation de noms vise à éviter les conflits avec les classes globales de même nom.  De plus, le nom du membre incorporé est le même que celui de `localClass`, sauf qu'il est précédé du préfixe « m\_x ».  
  
 Exemple :  
  
```  
BEGIN_INTERFACE_PART(MyAdviseSink, IAdviseSink)  
   STDMETHOD_(void,OnDataChange)(LPFORMATETC, LPSTGMEDIUM);  
   STDMETHOD_(void,OnViewChange)(DWORD, LONG);  
   STDMETHOD_(void,OnRename)(LPMONIKER);  
   STDMETHOD_(void,OnSave)();  
   STDMETHOD_(void,OnClose)();  
END_INTERFACE_PART(MyAdviseSink)  
```  
  
 définit une classe locale appelée XMyAdviseSink dérivée d'IAdviseSink, ainsi qu'un membre de la classe dans laquelle il est déclaré sous le nom m\_xMyAdviseSink.Note :  
  
> [!NOTE]
>  Les lignes commençant par `STDMETHOD`\_ sont pour l'essentiel copiées depuis OLE2.H et légèrement modifiées.  Le fait de les copier depuis OLE2. H permet de limiter des erreurs difficiles à corriger.  
  
### Description des macros BEGIN\_INTERFACE\_MAP et END\_INTERFACE\_MAP  
  
```  
  
              BEGIN_INTERFACE_MAP(   
   theClass,  
   baseClass   
) END_INTERFACE_MAP  
```  
  
## Notes  
  
#### Paramètres  
 `theClass`  
 Classe dans laquelle la table d'interface doit être définie.  
  
 `baseClass`  
 Classe de laquelle dérive `theClass`.  
  
## Notes  
 Les macros `BEGIN_INTERFACE_MAP` et `END_INTERFACE_MAP` sont utilisées dans le fichier d'implémentation pour définir véritablement la table d'interface.  À chaque interface implémentée correspond un ou plusieurs appels de macro `INTERFACE_PART`.  À chaque agrégation que la classe utilise correspond un appel de macro `INTERFACE_AGGREGATE`.  
  
### Description de la macro INTERFACE\_PART  
  
```  
  
              INTERFACE_PART(   
   theClass,  
   iid,   
   localClass   
)  
```  
  
## Notes  
  
#### Paramètres  
 `theClass`  
 Nom de la classe qui contient la table d'interface.  
  
 `iid`  
 `IID` qui doit être mappé à la classe incorporée.  
  
 `localClass`  
 Nom de la classe locale \(sans le « X »\).  
  
## Notes  
 Cette macro est utilisée entre la macro `BEGIN_INTERFACE_MAP` et la macro `END_INTERFACE_MAP` pour chaque interface que votre objet doit prendre en charge.  Elle permet de mapper un IID à un membre de la classe indiquée par `theClass` et `localClass`.  Le préfixe « m\_x » est automatiquement ajouté à `localClass`.  Notez que plusieurs `IID` peuvent être associés à un même membre.  Cela s'avère très utile quand vous implémentez uniquement une interface « la plus dérivée » et que vous voulez aussi fournir toutes les interfaces intermédiaires.  L'interface `IOleInPlaceFrameWindow` en constitue un bon exemple.  Sa hiérarchie se présente comme suit :  
  
```  
IUnknown  
    IOleWindow  
        IOleUIWindow  
            IOleInPlaceFrameWindow  
```  
  
 Si un objet implémente `IOleInPlaceFrameWindow`, un client peut appeler `QueryInterface` sur n'importe laquelle de ces interfaces : `IOleUIWindow`, `IOleWindow` ou [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509), en plus de l'interface « la plus dérivée » `IOleInPlaceFrameWindow` \(celle que vous implémentez réellement\).  Pour cela, vous pouvez utiliser plusieurs macros `INTERFACE_PART` pour mapper chaque interface de base à l'interface `IOleInPlaceFrameWindow` :  
  
 dans le fichier de définition de classe :  
  
```  
BEGIN_INTERFACE_PART(CMyFrameWindow, IOleInPlaceFrameWindow)  
```  
  
 dans le fichier d'implémentation de classe :  
  
```  
BEGIN_INTERFACE_MAP(CMyWnd, CFrameWnd)  
    INTERFACE_PART(CMyWnd, IID_IOleWindow, MyFrameWindow)  
    INTERFACE_PART(CMyWnd, IID_IOleUIWindow, MyFrameWindow)  
    INTERFACE_PART(CMyWnd, IID_IOleInPlaceFrameWindow, MyFrameWindow)  
END_INTERFACE_MAP  
```  
  
 L'infrastructure gère l'interface IUnknown, car elle est toujours nécessaire.  
  
### Description de la macro INTERFACE\_PART  
  
```  
  
              INTERFACE_AGGREGATE(   
   theClass,  
   theAggr   
)  
```  
  
## Notes  
  
#### Paramètres  
 `theClass`  
 Nom de la classe qui contient la table d'interface.  
  
 `theAggr`  
 Nom de la variable membre qui doit être agrégée.  
  
## Notes  
 Cette macro est utilisée pour indiquer à l'infrastructure que la classe utilise un objet d'agrégation.  Elle doit figurer entre les macros `BEGIN_INTERFACE_PART` et `END_INTERFACE_PART`.  Un objet d'agrégation est un objet distinct, dérivé d'[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  En utilisant une agrégation et la macro `INTERFACE_AGGREGATE`, vous pouvez faire apparaître toutes les interfaces prises en charge par l'agrégation comme étant directement prises en charge par l'objet.  L'argument `theAggr` est simplement le nom d'une variable membre de votre classe qui est dérivée d'[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) \(directement ou indirectement\).  Toutes les macros `INTERFACE_AGGREGATE` doivent suivre les macros `INTERFACE_PART` quand elles sont placées dans une table d'interface.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)
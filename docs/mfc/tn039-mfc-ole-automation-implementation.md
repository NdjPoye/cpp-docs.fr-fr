---
title: "TN039&#160;: impl&#233;mentation d&#39;Automation MFC/OLE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "Automation, interface COM MFC (points d'entrée)"
  - "IDispatch (interface)"
  - "MFC, prise en charge COM"
  - "MFC, OLE DB et"
  - "TN039"
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN039&#160;: impl&#233;mentation d&#39;Automation MFC/OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
## Présentation de OLE interface IDispatch  
 L'interface de `IDispatch` est le moyen par lequel les applications exposent des méthodes et des propriétés telles que d'autres applications telles que Visual Basic, ou d'autres langages, peuvent utiliser les fonctionnalités de l'application.  L'aspect le plus important de cette interface est la fonction **IDispatch::Invoke**.  MFC utilise des « tables de dispatch » pour implémenter **IDispatch::Invoke**.  La table de dispatch fournit des informations sur l'implémentation par MFC de la mise en page ou la « forme » de vos classes dérivées de `CCmdTarget`, de sorte qu'il peut manipuler directement les propriétés de l'objet, ou appeler les fonctions membres dans votre objet pour satisfaire les requêtes **IDispatch::Invoke**.  
  
 Pour la plupart, ClassWizard et MFC coopèrent pour masquer la plupart des détails de l'automation OLE du programmeur d'application.  Le programmeur privilégie la fonctionnalité réelle à exposer dans l'application et ne doit pas à se soucier des détails sous\-jacents.  
  
 Il existe des cas, toutefois, où il est nécessaire de comprendre ce que MFC fait en arrière\-plan.  Cette remarque traitera de comment le framework affecte **DISPID**s aux fonctions et propriétés membres.  La connaissance des usages d'algorithme MFC pour affecter **DISPID** n'est nécessaire que lorsque vous devez connaître l'ID, comme lorsque vous créez une « bibliothèque de types » pour les objets de votre application.  
  
## Attribution de MFC DISPID  
 Bien que l'utilisateur final de l'automatisaton \(un utilisateur Visual Basic, par exemple\), voit les noms réels de propriétés et méthodes où l'automation est activée dans leur code \(par exemple obj.ShowWindow\), l'implémentation **IDispatch::Invoke** n'accepte pas les noms réels.  Pour des raisons d'optimisation, cela accepte **DISPID**, qui est un « cookie magique » 32 bits qui décrit la méthode ou la propriété qui doivent être accessibles.  Ces valeurs de **DISPID** sont retournées à partir de l'implémentation `IDispatch` via une autre méthode, appelée **IDispatch::GetIDsOfNames**.  Une application cliente appelle `GetIDsOfNames` une fois pour chaque membre ou propriété ou qu'il prévoit d'accéder, et les met en cache pour des appels ultérieurs à **IDispatch::Invoke**.  De cette façon, la recherche coûteuse de chaîne n'est effectuée qu'une fois par utilisation d'objets, au lieu d'une fois par appel **IDispatch::Invoke**.  
  
 MFC détermine les **DISPID** pour chaque méthode et propriété basées sur deux choses :  
  
-   La distance depuis le haut de la table de dispatch \(par rapport à 1\)  
  
-   La distance de la table de dispatch de la classe depuis la classe la plus dérivée \(par rapport à 0\)  
  
 **DISPID** est divisé en deux parties.  Le **LOWORD** de **DISPID** contient le premier composant, la distance depuis le haut de la table de dispatch.  Le **HIWORD** contient la distance de la classe la plus dérivée.  Par exemple :  
  
```  
class CDispPoint : public CCmdTarget  
{  
public:  
    short m_x, m_y;  
    ...  
    DECLARE_DISPATCH_MAP()  
    ...  
};  
  
class CDisp3DPoint : public CDispPoint  
{  
public:  
    short m_z;  
    ...  
    DECLARE_DISPATCH_MAP()  
    ...  
};  
  
BEGIN_DISPATCH_MAP(CDispPoint, CCmdTarget)  
    DISP_PROPERTY(CDispPoint, "x", m_x, VT_I2)  
    DISP_PROPERTY(CDispPoint, "y", m_y, VT_I2)  
END_DISPATCH_MAP()  
  
BEGIN_DISPATCH_MAP(CDisp3DPoint, CDispPoint)  
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)  
END_DISPATCH_MAP()  
```  
  
 Comme vous pouvez le voir, il existe deux classes, qui exposent des interfaces d'automatisaon OLE.  Une de ces classes est dérivée de l'autre et accroît ainsi la fonctionnalité de la classe de base, notamment la partie d'automisation OLE \(propriétés « x » et « y » dans ce cas\).  
  
 MFC génère **DISPID**s pour la classe CDispPoint comme suit :  
  
```  
property X    (DISPID)0x00000001  
property Y    (DISPID)0x00000002  
```  
  
 Comme les propriétés ne figurent pas dans une classe de base, le **HIWORD** de **DISPID** est toujours zéro \(la distance à la classe la plus dérivée pour CDispPoint est zéro\).  
  
 MFC génère **DISPID**s pour la classe CDisp3DPoint comme suit :  
  
```  
property Z    (DISPID)0x00000001  
property X    (DISPID)0x00010001  
property Y    (DISPID)0x00010002  
```  
  
 La propriété Z reçoit un **DISPID** avec **HIWORD** zéro car elle est définie dans la classe qui expose les propriétés, CDisp3DPoint.  Puisque les propriétés X et Y sont définies dans une classe de base, le **HIWORD** de **DISPID** est 1, puisque la classe dans laquelle ces propriétés sont définies est à une distance d'une dérivation de la classe la plus dérivée.  
  
> [!NOTE]
>  **LOWORD** est toujours déterminé par la position de la carte, même s'il existe des entrées dans la carte avec des **DISPID** explicites \(voir la section suivante pour plus d'informations sur les versions **\_ID** de macros `DISP_PROPERTY` et `DISP_FUNCTION` \).  
  
## Fonctionnalités avancées de dispatch de MFC  
 Il existe de nombreuses fonctionnalités supplémentaires que ClassWizard ne prend pas en charge avec cette version de Visual C\+\+.  ClassWizard prend en charge `DISP_FUNCTION`, `DISP_PROPERTY`, et `DISP_PROPERTY_EX` définissant une méthode, une propriété de variable membre, et une propriété de fonction membre get\/set, respectivement.  Ces fonctions sont généralement tout ce qui est nécessaire pour créer la plupart des serveurs Automation.  
  
 Les macros supplémentaires suivantes peuvent être utilisées lorsque les macros prises en charge par ClassWizard ne sont pas appropriées : `DISP_PROPERTY_NOTIFY`, et `DISP_PROPERTY_PARAM`.  
  
## DISP PROPERTY NOTIFY \- description de macro  
  
```  
  
        DISP_PROPERTY_NOTIFY(   
   theClass,   
   pszName,   
   memberName,   
   pfnAfterSet,   
   vtPropType   
)  
```  
  
## Remarques  
  
### Paramètres  
 `theClass`  
 Nom de la classe.  
  
 `pszName`  
 Nom externe de la propriété.  
  
 `memberName`  
 Nom de la variable membre dont la propriété est stockée.  
  
 `pfnAfterSet`  
 Nom de la fonction membre à appeler lorsque la propriété est modifiée.  
  
 `vtPropType`  
 Valeur qui spécifie le type de propriété.  
  
## Remarques  
 La macro est comme `DISP_PROPERTY`, sauf qu'elle reçoit un argument supplémentaire.  L'argument supplémentaire, *pfnAfterSet,* doit être une fonction membre qui ne retourne rien et ne requiert aucun paramètre, 'void OnPropertyNotify\(\)'.  Ce est appelé **une fois** la variable membre modifiée.  
  
## DISP PROPERTY PARAM \- macro description  
  
```  
  
        DISP_PROPERTY_PARAM(   
   theClass,  
   pszName,  
   pfnGet,  
   pfnSet,  
   vtPropType,  
   vtsParams   
)  
```  
  
## Remarques  
  
### Paramètres  
 `theClass`  
 Nom de la classe.  
  
 `pszName`  
 Nom externe de la propriété.  
  
 `memberGet`  
 Nom de la fonction membre utilisée pour récupérer la propriété.  
  
 `memberSet`  
 Nom de la fonction membre utilisée pour définir la propriété.  
  
 `vtPropType`  
 Valeur qui spécifie le type de propriété.  
  
 `vtsParams`  
 Chaîne de VTS\_ séparés par des espaces pour chaque paramètre.  
  
## Remarques  
 Comme la macro `DISP_PROPERTY_EX`, cette macro définit une propriété acessible avec des fonctions membre Get et Set séparées.  La macro, toutefois, vous permet de spécifier une liste de paramètres pour la propriété.  Cette option est utile pour implémenter les propriétés indexées ou paramétrables d'une autre façon.  Les paramètres sont toujours placés en premier, suivis de la nouvelle valeur de la propriété.  Par exemple :  
  
```  
DISP_PROPERTY_PARAM(CMyObject, "item", GetItem, SetItem, VT_DISPATCH,    VTS_I2 VTS_I2)  
```  
  
 correspondrait aux fonctions membres Get et Set :  
  
```  
LPDISPATCH CMyObject::GetItem(short row, short col)  
void CMyObject::SetItem(short row, short col, LPDISPATCH newValue)  
```  
  
## DISP\_XXXX\_ID — macro descriptions  
  
```  
  
        DISP_FUNCTION_ID(   
   theClass,  
   pszName,  
   dispid,  
   pfnMember,  
   vtRetVal,  
   vtsParams   
) DISP_PROPERTY_ID(   
   theClass,  
   pszName,  
   dispid,  
   memberName,  
   vtPropType   
) DISP_PROPERTY_NOTIFY_ID(   
   theClass,  
   pszName,  
   dispid,  
   memberName,  
   pfnAfterSet,  
   vtPropType   
) DISP_PROPERTY_EX_ID(   
   theClass,  
   pszName,  
   dispid,  
   pfnGet,  
   pfnSet,  
   vtPropType   
) DISP_PROPERTY_PARAM_ID(   
   theClass,  
   pszName,  
   dispid,  
   pfnGet,  
   pfnSet,  
   vtPropType,  
   vtsParams   
)  
```  
  
## Remarques  
  
### Paramètres  
 `theClass`  
 Nom de la classe.  
  
 `pszName`  
 Nom externe de la propriété.  
  
 `dispid`  
 Le DISPID fixe pour la propriété ou la méthode.  
  
 `pfnGet`  
 Nom de la fonction membre utilisée pour récupérer la propriété.  
  
 `pfnSet`  
 Nom de la fonction membre utilisée pour définir la propriété.  
  
 `memberName`  
 Nom des variables membres à laquelle mapper la propriété  
  
 `vtPropType`  
 Valeur qui spécifie le type de propriété.  
  
 `vtsParams`  
 Chaîne de VTS\_ séparés par des espaces pour chaque paramètre.  
  
## Remarques  
 Les macros vous permettent de spécifier un **DISPID** au lieu de laisser MFC en attribuer automatiquement un.  Les macros avancées ont le même nom sauf que l'ID est ajouté au nom de macro \(ex :  **DISP\_PROPERTY\_ID**\) et l'ID est déterminé par le paramètre juste après le paramètre `pszName`.  Voir AFXDISP.H pour plus d'informations sur les macros.  Les entrées d'**\_ID** doivent être placées à la fin de la table de dispatch.  Elles affectent la génération automatique de **DISPID** de la même manière qu'une version sans **\_ID** de macros \(les **DISPID** sont déterminés par la position\).  Par exemple :  
  
```  
BEGIN_DISPATCH_MAP(CDisp3DPoint, CCmdTarget)  
    DISP_PROPERTY(CDisp3DPoint, "y", m_y, VT_I2)  
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)  
    DISP_PROPERTY_ID(CDisp3DPoint, "x", 0x00020003, m_x, VT_I2)  
END_DISPATCH_MAP()  
```  
  
 MFC génère DISPIDs pour la classe CDisp3DPoint comme suit :  
  
```  
property X    (DISPID)0x00020003  
property Y    (DISPID)0x00000002  
property Z     (DISPID)0x00000001  
```  
  
 Spécifier un **DISPID** fixe est utile pour assurer la compatibilité descendante vers une interface de dispatch déjà existante, ou pour implémenter certaines méthodes et propriétés systèmes définies \(généralement indiquées par un **DISPID** négatif, comme la collection **DISPID\_NEWENUM** \).  
  
#### Récupérer l'interface IDispatch pour un COleClientItem  
 De nombreux serveurs prennent en charge l'automation dans leurs objets document, avec la fonctionnalité serveur OLE.  Pour accéder à cette interface Automation, il est nécessaire d'accéder directement à la variable membre de **COleClientItem::m\_lpObject**.  Le code ci\-dessous récupère l'interface `IDispatch` pour un objet dérivé de `COleClientItem`.  Vous pouvez incorporer le code ci\-dessous dans votre application si trouvez cette fonctionnalité nécessaire :  
  
```  
LPDISPATCH CMyClientItem::GetIDispatch()  
{  
    ASSERT_VALID(this);  
    ASSERT(m_lpObject != NULL);  
  
    LPUNKNOWN lpUnk = m_lpObject;  
  
    Run();    // must be running  
  
    LPOLELINK lpOleLink = NULL;  
    if (m_lpObject->QueryInterface(IID_IOleLink,   
        (LPVOID FAR*)&lpOleLink) == NOERROR)  
    {  
        ASSERT(lpOleLink != NULL);  
        lpUnk = NULL;  
        if (lpOleLink->GetBoundSource(&lpUnk) != NOERROR)  
        {  
            TRACE0("Warning: Link is not connected!\n");  
            lpOleLink->Release();  
            return NULL;  
        }  
        ASSERT(lpUnk != NULL);  
    }  
  
    LPDISPATCH lpDispatch = NULL;  
    if (lpUnk->QueryInterface(IID_IDispatch, &lpDispatch)   
        != NOERROR)  
    {  
        TRACE0("Warning: does not support IDispatch!\n");  
        return NULL;  
    }  
  
    ASSERT(lpDispatch != NULL);  
    return lpDispatch;  
}  
```  
  
 L'interface de dispatch retournée par cette fonction peut être utilisée directement ou attachée à `COleDispatchDriver` pour l'accès de type sécurisé.  Si vous l'utilisez directement, assurez\-vous que vous appelez son membre **Release** lorsque de l'utilisation du pointeur \(le destructeur `COleDispatchDriver` fait cela par défaut\).  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)
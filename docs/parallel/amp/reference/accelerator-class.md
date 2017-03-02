---
title: Accelerator, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::accelerator
dev_langs:
- C++
helpviewer_keywords:
- accelerator class
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
caps.latest.revision: 29
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: b1bdd7f6979094658d1de6f9690bc44dc50ee8bb
ms.lasthandoff: 02/24/2017

---
# <a name="accelerator-class"></a>accelerator, classe
Un raccourci est une fonctionnalité de matériel qui est optimisée pour l’informatique parallèle de données. Un accélérateur peut être un périphérique connecté à un bus PCIe (par exemple, une carte GPU), ou il peut s’agir d’une instruction étendue définie sur l’unité centrale principale.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class accelerator;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Accelerator, constructeur](#ctor)|Initialise une nouvelle instance de la classe `accelerator`.|  
|[~ accelerator, destructeur](#ctor)|Détruit le `accelerator` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CREATE_VIEW (méthode)](#create_view)|Crée et retourne un `accelerator_view` objet sur cet accélérateur.|  
|[get_all (méthode)](#get_all)|Retourne un vecteur de `accelerator` objets qui représentent tous les accélérateurs disponibles.|  
|[get_auto_selection_view (méthode)](#get_auto_selection_view)|Retourne la sélection automatique de `accelerator_view`.|  
|[get_dedicated_memory (méthode)](#get_dedicated_memory)|Retourne la mémoire dédiée pour le `accelerator`, en kilo-octets.|  
|[get_default_cpu_access_type (méthode)](#get_default_cpu_access_type)|Retourne la valeur par défaut [access_type](concurrency-namespace-enums-amp.md#access_type) pour les mémoires tampons créées sur cet accélérateur.|  
|[get_default_view (méthode)](#get_default_view)|Retourne la valeur par défaut `accelerator_view` objet auquel est associé le `accelerator`.|  
|[get_Description (méthode)](#get_description)|Retourne une courte description de le `accelerator` périphérique.|  
|[get_device_path (méthode)](#get_device_path)|Retourne le chemin d’accès de l’appareil.|  
|[get_has_display (méthode)](#get_has_display)|Détermine si le `accelerator` est attaché à un affichage.|  
|[get_is_debug (méthode)](#get_is_debug)|Détermine si le `accelerator` a la couche de débogage est activée pour le rapport d’erreur étendu.|  
|[get_is_emulated (méthode)](#get_is_emulated)|Détermine si le `accelerator` est émulée.|  
|[get_supports_cpu_shared_memory (méthode)](#get_supports_cpu_shared_memory)|Détermine si le `accelerator` prend en charge de la mémoire partagée|  
|[get_supports_double_precision (méthode)](#get_supports_double_precision)|Détermine si le `accelerator` est attaché à un affichage.|  
|[get_supports_limited_double_precision (méthode)](#get_supports_limited_double_precision)|Détermine si le `accelerator` prend en charge pour les fonctions mathématiques double précision limitée.|  
|[get_version (méthode)](#get_version)|Retourne la version de la `accelerator`.|  
|[set_default (méthode)](#set_default)|Retourne le chemin d’accès de l’accélérateur par défaut.|  
|[set_default_cpu_access_type (méthode)](#set_default_cpu_access_type)|Définit l’unité centrale par défaut [access_type](concurrency-namespace-enums-amp.md#access_type)pour les tableaux et les allocations de mémoire implicites effectuées sur ce `accelerator`.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[opérateur ! =, opérateur](#operator_neq)|Compare cette `accelerator` objet avec une autre et retourne `false` si elles sont identiques ; sinon, retourne `true`.|  
|[opérateur =, opérateur](#operator_eq)|Copie le contenu de l’objet `accelerator` objet à celui-ci.|  
|[opérateur ==, opérateur](#operator_eq_eq)|Compare cette `accelerator` objet avec une autre et retourne `true` si elles sont identiques ; sinon, retourne `false`.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[cpu_accelerator (donnée membre)](#cpu_accelerator)|Obtient une chaîne constante pour le processeur `accelerator`.|  
|[dedicated_memory (donnée membre)](#dedicated_memory)|Obtient la mémoire dédiée pour le `accelerator`, en kilo-octets.|  
|[default_accelerator (donnée membre)](#default_accelerator)|Obtient une chaîne constante pour la valeur par défaut `accelerator`.|  
|[default_cpu_access_type (donnée membre)](#default_cpu_access_type)|Obtient ou définit l’unité centrale par défaut [access_type](concurrency-namespace-enums-amp.md#access_type)pour les tableaux et les allocations de mémoire implicites effectuées sur ce `accelerator`.|  
|[default_view (donnée membre)](#default_view)|Obtient la valeur par défaut `accelerator_view` objet auquel est associé le `accelerator`.|  
|[Description des membres de données](#description)|Obtient une brève description de le `accelerator` périphérique.|  
|[chemin_unité membre de données](#device_path)|Obtient le chemin d’accès de l’appareil.|  
|[direct3d_ref (donnée membre)](#direct3d_ref)|Obtient une chaîne constante pour obtenir une référence Direct3D `accelerator`.|  
|[direct3d_warp (donnée membre)](#direct3d_warp)|Obtient la chaîne constante pour un `accelerator` de l’objet que vous pouvez utiliser pour l’exécution de code C++ AMP sur les processeurs multicœurs qui utilisent les Extensions Streaming SIMD (SSE).|  
|[has_display (donnée membre)](#has_display)|Obtient une valeur booléenne qui indique si la `accelerator` est attaché à un affichage.|  
|[is_debug (donnée membre)](#is_debug)|Indique si le `accelerator` a la couche de débogage est activée pour le rapport d’erreur étendu.|  
|[is_emulated (donnée membre)](#is_emulated)|Indique si la `accelerator` est émulée.|  
|[supports_cpu_shared_memory (donnée membre)](#supports_cpu_shared_memory)|Indique si le `accelerator` prend en charge de la mémoire partagée.|  
|[supports_double_precision (donnée membre)](#supports_double_precision)|Indique si l’accélérateur prend en charge les mathématiques double précision.|  
|[supports_limited_double_precision (donnée membre)](#supports_limited_double_precision)|Indique si l’accélérateur est limitée à la prise en charge pour les fonctions mathématiques double précision.|  
|[Membre de données de version](#version)|Obtient la version de la `accelerator`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `accelerator`  
  
## <a name="remarks"></a>Remarques  
 Un raccourci est une fonctionnalité de matériel qui est optimisée pour l’informatique parallèle de données. Un raccourci est souvent un processeur séparé, mais il peut également être une entité côté hôte virtuelle comme un périphérique DirectX REF, une chaîne (un appareil côté UC est accéléré au moyen d’instructions SSE), ou que le processeur lui-même.  
  
 Vous pouvez construire une `accelerator` objet par l’énumération des périphériques disponibles, ou en obtenant le périphérique par défaut, l’appareil de référence ou le périphérique de distorsion.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amprt.h  
  
 **Espace de noms :** Concurrency  
  
##  <a name="dtor"></a></a> ~ accelerator 

 Détruit le `accelerator` objet.  
  
```  
~accelerator();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-namectora-accelerator"></a><a name="ctor"></a>accélérateur 

 Initialise une nouvelle instance de la [accelerator (classe)](accelerator-class.md).  
  
```  
accelerator();

 
explicit accelerator(const std::wstring& _Device_path);

 
accelerator(const accelerator& _Other);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Device_path`  
 Le chemin d’accès de l’unité physique.  
  
 `_Other`  
 L’accélérateur à copier.  
  
##  <a name="a-namecpuacceleratora-cpuaccelerator"></a><a name="cpu_accelerator"></a>cpu_accelerator 

 Obtient une chaîne constante pour l’accélérateur CPU.  
  
```  
static const wchar_t cpu_accelerator[];  
```  
  
##  <a name="a-namecreateviewa-createview"></a><a name="create_view"></a>CREATE_VIEW 

 Crée et retourne un `accelerator_view` objet sur cet accélérateur, l’utilisation du mode de file d’attente spécifié. Lorsque le mode de file d’attente n’est pas spécifié, la nouvelle `accelerator_view` utilise le [queuing_mode::immediate](concurrency-namespace-enums-amp.md#queuing_mode) mode file d’attente.  
  
```  
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```  
  
### <a name="parameters"></a>Paramètres  
 `qmode`  
 Le mode de file d’attente.  
  
### <a name="return-value"></a>Valeur de retour  
 Un nouveau `accelerator_view` objet sur cet accélérateur, l’utilisation du mode de file d’attente spécifié.  
  
##  <a name="a-namededicatedmemorya-dedicatedmemory"></a><a name="dedicated_memory"></a>dedicated_memory 

 Obtient la mémoire dédiée pour le `accelerator`, en kilo-octets.  
  
```  
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;  
```  
  
##  <a name="a-namedefaultacceleratora-defaultaccelerator"></a><a name="default_accelerator"></a>default_accelerator 

 Obtient une chaîne constante pour la valeur par défaut `accelerator`.  
  
```  
static const wchar_t default_accelerator[];  
```  
  
##  <a name="a-namedefaultcpuaccesstypea-defaultcpuaccesstype"></a><a name="default_cpu_access_type"></a>default_cpu_access_type 

 La valeur par défaut processeur [access_type](concurrency-namespace-enums-amp.md#access_type)pour les tableaux et les allocations de mémoire implicites effectuées sur cette ce `accelerator`.  
  
```  
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;  
```  
  
##  <a name="a-namedefaultviewa-defaultview"></a><a name="default_view"></a>default_view 

 Obtient la vue d’accélérateur par défaut qui est associée à le `accelerator`.  
  
```  
__declspec(property(get= get_default_view)) accelerator_view default_view;  
```  
  
##  <a name="a-namedescriptiona-description"></a><a name="description"></a>Description 

 Obtient une brève description de le `accelerator` périphérique.  
  
```  
__declspec(property(get= get_description)) std::wstring description;  
```  
  
##  <a name="a-namedevicepatha-devicepath"></a><a name="device_path"></a>chemin_unité 

 Obtient le chemin d’accès de l’accélérateur. Le chemin d’accès est unique sur le système.  
  
```  
__declspec(property(get= get_device_path)) std::wstring device_path;  
```  
  
##  <a name="a-namedirect3drefa-direct3dref"></a><a name="direct3d_ref"></a>direct3d_ref 

 Obtient une chaîne constante pour un accélérateur de référence Direct3D.  
  
```  
static const wchar_t direct3d_ref[];  
```  
  
##  <a name="a-namedirect3dwarpa-direct3dwarp"></a><a name="direct3d_warp"></a>direct3d_warp 

 Obtient la chaîne constante pour un `accelerator` de l’objet que vous pouvez utiliser pour l’exécution de votre code C++ AMP sur les processeurs multicœurs à l’aide des Extensions Streaming SIMD (SSE).  
  
```  
static const wchar_t direct3d_warp[];  
```  
  
##  <a name="a-namegetalla-getall"></a><a name="get_all"></a>get_all 

 Retourne un vecteur de `accelerator` objets qui représentent tous les accélérateurs disponibles.  
  
```  
static inline std::vector<accelerator> get_all();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le vecteur d’accélérateurs disponibles  
  
##  <a name="a-namegetautoselectionviewa-getautoselectionview"></a><a name="get_auto_selection_view"></a>get_auto_selection_view 

 Retourne l’accelerator_view de sélection automatique, qui une fois spécifié en tant que les résultats de la cible parallel_for_each dans la cible accelerator_view pour exécuter le noyau parallel_for_each être sélectionnés automatiquement par le runtime. À d’autres fins, l’accelerator_view retourné par cette méthode est identique à la valeur par défaut accelerator_view de l’accélérateur par défaut  
  
```  
static accelerator_view __cdecl get_auto_selection_view();
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’accelerator_view de sélection automatique.  
  
##  <a name="a-namegetdedicatedmemorya-getdedicatedmemory"></a><a name="get_dedicated_memory"></a>get_dedicated_memory 

 Retourne la mémoire dédiée pour le `accelerator`, en kilo-octets.  
  
```  
size_t get_dedicated_memory() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 La mémoire dédiée pour le `accelerator`, en kilo-octets.  
  
##  <a name="a-namegetdefaultcpuaccesstypea-getdefaultcpuaccesstype"></a><a name="get_default_cpu_access_type"></a>get_default_cpu_access_type 

 Obtient l’access_type du processeur par défaut pour les mémoires tampons créées sur cet accélérateur  
  
```  
access_type get_default_cpu_access_type() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’access_type du processeur par défaut pour les mémoires tampons créées sur cet accélérateur.  
  
##  <a name="a-namegetdefaultviewa-getdefaultview"></a><a name="get_default_view"></a>get_default_view 

 Retourne la valeur par défaut `accelerator_view` objet auquel est associé le `accelerator`.  
  
```  
accelerator_view get_default_view() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur par défaut `accelerator_view` objet auquel est associé le `accelerator`.  
  
##  <a name="a-namegetdescriptiona-getdescription"></a><a name="get_description"></a>get_Description 

 Retourne une courte description de le `accelerator` périphérique.  
  
```  
std::wstring get_description() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une brève description de le `accelerator` périphérique.  
  
##  <a name="a-namegetdevicepatha-getdevicepath"></a><a name="get_device_path"></a>get_device_path 

 Retourne le chemin d’accès de l’accélérateur. Le chemin d’accès est unique sur le système.  
  
```  
std::wstring get_device_path() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le chemin d’accès d’instance périphérique unique à l’échelle du système.  
  
##  <a name="a-namegethasdisplaya-gethasdisplay"></a><a name="get_has_display"></a>get_has_display 

 Retourne une valeur booléenne qui indique si le `accelerator` peut envoyer la sortie vers un affichage.  
  
```  
bool get_has_display() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le `accelerator` peut envoyer la sortie vers un affichage ; sinon, `false`.  
  
##  <a name="a-namegetisdebuga-getisdebug"></a><a name="get_is_debug"></a>get_is_debug 

 Détermine si le `accelerator` a la couche de débogage est activée pour le rapport d’erreur étendu.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le `accelerator` a la couche de débogage est activée pour le rapport d’erreur étendu. Sinon, `false`.  
  
##  <a name="a-namegetisemulateda-getisemulated"></a><a name="get_is_emulated"></a>get_is_emulated 

 Détermine si le `accelerator` est émulée.  
  
```  
bool get_is_emulated() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si la `accelerator` est émulée. Sinon, `false`.  
  
##  <a name="a-namegetsupportscpusharedmemorya-getsupportscpusharedmemory"></a><a name="get_supports_cpu_shared_memory"></a>get_supports_cpu_shared_memory 

 Retourne une valeur booléenne indiquant si l’accélérateur prend en charge la mémoire accessible par l’accélérateur et du processeur.  
  
```  
bool get_supports_cpu_shared_memory() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si l’accélérateur prend en charge la mémoire partagée de processeur ; dans le cas contraire, `false`.  
  
##  <a name="a-namegetsupportsdoubleprecisiona-getsupportsdoubleprecision"></a><a name="get_supports_double_precision"></a>get_supports_double_precision 

 Retourne une valeur booléenne qui indique si l’accélérateur prend en charge le double mathématique de précision, y compris les fondus multiplier ajouter (FMA), division, réciproque et effectuer un cast entre `int` et `double`.  
  
```  
bool get_supports_double_precision() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si l’accélérateur prend en charge le double mathématique de précision ; dans le cas contraire, `false`.  
  
##  <a name="a-namegetsupportslimiteddoubleprecisiona-getsupportslimiteddoubleprecision"></a><a name="get_supports_limited_double_precision"></a>get_supports_limited_double_precision 

 Retourne une valeur booléenne qui indique si l’accélérateur est limitée à la prise en charge pour le calcul de la précision double. Si l’accélérateur est uniquement prise en charge limitée, puis fusionné multiplier ajouter (FMA), division, réciproque et effectuer un cast entre `int` et `double` ne sont pas pris en charge.  
  
```  
bool get_supports_limited_double_precision() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si l’accélérateur a limité la prise en charge de double mathématique de précision ; dans le cas contraire, `false`.  
  
##  <a name="a-namegetversiona-getversion"></a><a name="get_version"></a>get_version 

 Retourne la version de la `accelerator`.  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 La version de la `accelerator`.  
  
##  <a name="a-namehasdisplaya-hasdisplay"></a><a name="has_display"></a>has_display 

 Obtient une valeur booléenne qui indique si le `accelerator` peut envoyer la sortie vers un affichage.  
  
```  
__declspec(property(get= get_has_display)) bool has_display;  
```  
  
##  <a name="a-nameisdebuga-isdebug"></a><a name="is_debug"></a>is_debug 

 Obtient une valeur booléenne qui indique si le `accelerator` a la couche de débogage est activée pour le rapport d’erreur étendu.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameisemulateda-isemulated"></a><a name="is_emulated"></a>is_emulated 

 Obtient une valeur booléenne qui indique si la `accelerator` est émulée.  
  
```  
__declspec(property(get= get_is_emulated)) bool is_emulated;  
```  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>opérateur ! = 

 Compare cette `accelerator` objet avec une autre et retourne `false` si elles sont identiques ; sinon, retourne `true`.  
  
```  
bool operator!= (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator` objet à comparer avec celle-ci.  
  
### <a name="return-value"></a>Valeur de retour  
 `false`Si les deux `accelerator` objets sont identiques ; sinon, `true`.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>opérateur = 

 Copie le contenu de l’objet `accelerator` objet à celui-ci.  
  
```  
accelerator& operator= (const accelerator& _Other);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator` objet d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à ce `accelerator` objet.  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>opérateur == 

 Compare cette `accelerator` objet avec une autre et retourne `true` si elles sont identiques ; sinon, retourne `false`.  
  
```  
bool operator== (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator` objet à comparer avec celle-ci.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si l’autre `accelerator` objet est identique à ce `accelerator` objet ; sinon, `false`.  
  
##  <a name="a-namesetdefaulta-setdefault"></a><a name="set_default"></a>set_default 

 Définit l’accélérateur par défaut à utiliser pour toute opération qui utilise implicitement l’accélérateur par défaut. Cette méthode ne réussit que si l’accélérateur par défaut sélectionné de runtime n’a pas déjà été utilisé dans une opération qui utilise implicitement l’accélérateur par défaut  
  
```  
static inline bool set_default(std::wstring _Path);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Path`  
 Le chemin d’accès à l’accélérateur.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si l’appel aboutit à la définition de l’accélérateur par défaut. Sinon, `false`.  
  
##  <a name="a-namesetdefaultcpuaccesstypea-setdefaultcpuaccesstype"></a><a name="set_default_cpu_access_type"></a>set_default_cpu_access_type 

 Définissez l’access_type du processeur par défaut pour les tableaux créés sur cet accélérateur ou des allocations de mémoire implicites comme partie d’array_views accessible sur ce cet accélérateur. Cette méthode ne réussit que si la default_cpu_access_type pour l’accélérateur n’a pas encore été remplacé par un appel précédent à cette méthode et le default_cpu_access_type d’exécution sélectionnée pour cet accélérateur n’a pas encore été utilisé pour allouer un tableau ou d’une allocation de mémoire implicites sauvegarde un array_view accédé sur cet accélérateur.  
  
```  
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Default_cpu_access_type`  
 L’access_type du processeur par défaut à utiliser pour les allocations de mémoire tableau/array_view sur cet accélérateur.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur booléenne indiquant si l’access_type du processeur par défaut pour l’accélérateur a été correctement définie.  
  
##  <a name="a-namesupportscpusharedmemorya-supportscpusharedmemory"></a><a name="supports_cpu_shared_memory"></a>supports_cpu_shared_memory 

 Obtient une valeur booléenne indiquant si le `accelerator` prend en charge de la mémoire partagée.  
  
```  
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;  
```  
  
##  <a name="a-namesupportsdoubleprecisiona-supportsdoubleprecision"></a><a name="supports_double_precision"></a>supports_double_precision 

 Obtient une valeur booléenne qui indique si l’accélérateur prend en charge les mathématiques double précision.  
  
```  
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;  
```  
  
##  <a name="a-namesupportslimiteddoubleprecisiona-supportslimiteddoubleprecision"></a><a name="supports_limited_double_precision"></a>supports_limited_double_precision 

 Obtient une valeur booléenne qui indique si l’accélérateur est limitée à la prise en charge pour le calcul de la précision double. Si l’accélérateur est uniquement prise en charge limitée, puis fusionné multiplier ajouter (FMA), division, réciproque et effectuer un cast entre `int` et `double` ne sont pas pris en charge.  
  
```  
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;  
```  
  
##  <a name="a-nameversiona-version"></a><a name="version"></a>Version 

 Obtient la version de la `accelerator`.  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="dtor"></a></a> ~ accelerator_view 

 Détruit le [accelerator_view](accelerator-view-class.md) objet.  
  
```  
~accelerator_view();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-nameacceleratora-accelerator"></a><a name="accelerator"></a>accélérateur 

 Obtient le `accelerator` de l’objet pour le [accelerator_view](accelerator-view-class.md) objet.  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
##  <a name="a-namectora-acceleratorview"></a><a name="ctor"></a>accelerator_view 

 Initialise une nouvelle instance de la [accelerator_view](accelerator-view-class.md) classe en copiant une existante `accelerator_view` objet.  
  
```  
accelerator_view(const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator_view` objet à copier.  
  
##  <a name="a-namecreatemarkera-createmarker"></a><a name="create_marker"></a>create_marker 

 Retourne un futur pour effectuer le suivi de l’achèvement de toutes les commandes envoyées jusqu'à présent à ce `accelerator_view` objet.  
  
```  
concurrency::completion_future create_marker();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un futur pour effectuer le suivi de l’achèvement de toutes les commandes envoyées jusqu'à présent à ce `accelerator_view` objet.  
  
##  <a name="a-nameflusha-flush"></a><a name="flush"></a>Vider 

 Envoie toutes les commandes en attente en attente pour le [accelerator_view](accelerator-view-class.md) objet à l’accélérateur pour l’exécution.  
  
```  
void flush();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `void`.  
  
##  <a name="a-namegetacceleratora-getaccelerator"></a><a name="get_accelerator"></a>get_accelerator 

 Retourne le `accelerator` de l’objet pour le [accelerator_view](accelerator-view-class.md) objet.  
  
```  
accelerator get_accelerator() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le `accelerator` de l’objet pour le `accelerator_view` objet.  
  
##  <a name="a-namegetisautoselectiona-getisautoselection"></a><a name="get_is_auto_selection"></a>get_is_auto_selection 

 Retourne une valeur booléenne qui indique si le runtime sélectionne automatiquement un accélérateur approprié lorsque l’accelerator_view est transmis à un [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each).  
  
```  
bool get_is_auto_selection() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le runtime va sélectionner automatiquement un accélérateur approprié ; dans le cas contraire, `false`.  
  
##  <a name="a-namegetisdebuga-getisdebug"></a><a name="get_is_debug"></a>get_is_debug 

 Retourne une valeur booléenne qui indique si le [accelerator_view](accelerator-view-class.md) objet a la couche de débogage est activée pour le rapport d’erreur étendu.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur booléenne qui indique si le `accelerator_view` objet a la couche de débogage est activée pour le rapport d’erreur étendu.  
  
##  <a name="a-namegetqueuingmodea-getqueuingmode"></a><a name="get_queuing_mode"></a>get_queuing_mode 

 Retourne le mode file d’attente pour le [accelerator_view](accelerator-view-class.md) objet.  
  
```  
queuing_mode get_queuing_mode() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le mode de file d’attente pour le `accelerator_view` objet.  
  
##  <a name="a-namegetversiona-getversion"></a><a name="get_version"></a>get_version 

 Retourne la version de la [accelerator_view](accelerator-view-class.md).  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 La version de la `accelerator_view`.  
  
##  <a name="a-nameisautoselectiona-isautoselection"></a><a name="is_auto_selection"></a>is_auto_selection 

 Obtient une valeur booléenne qui indique si le runtime sélectionne automatiquement un accélérateur approprié lorsque l’accelerator_view est transmis à un [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each).  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
##  <a name="a-nameisdebuga-isdebug"></a><a name="is_debug"></a>is_debug 

 Obtient une valeur booléenne qui indique si le [accelerator_view](accelerator-view-class.md) objet a la couche de débogage est activée pour le rapport d’erreur étendu.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>opérateur ! = 

 Compare cette [accelerator_view](accelerator-view-class.md) objet avec une autre et retourne `false` si elles sont identiques ; sinon, retourne `true`.  
  
```  
bool operator!= (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator_view` objet à comparer avec celle-ci.  
  
### <a name="return-value"></a>Valeur de retour  
 `false` si les deux objets sont identiques ; sinon, `true`.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>opérateur = 

 Copie le contenu de l’objet [accelerator_view](accelerator-view-class.md) objet dans celui-ci.  
  
```  
accelerator_view& operator= (const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator_view` objet d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à la modification `accelerator_view` objet.  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>opérateur == 

 Compare cette [accelerator_view](accelerator-view-class.md) objet avec une autre et retourne `true` si elles sont identiques ; sinon, retourne `false`.  
  
```  
bool operator== (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator_view` objet à comparer avec celle-ci.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si les deux objets sont identiques ; sinon, `false`.  
  
##  <a name="a-namequeuingmodea-queuingmode"></a><a name="queuing_mode"></a>queuing_mode 

 Obtient le mode de file d’attente pour le [accelerator_view](accelerator-view-class.md) objet.  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
##  <a name="a-nameversiona-version"></a><a name="version"></a>Version 

 Obtient la version de la [accelerator_view](accelerator-view-class.md).  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>attente 

 Attend que toutes les commandes envoyées à la [accelerator_view](accelerator-view-class.md) objet se termine.  
  
```  
void wait();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `void`.  
  
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)


---
title: "accelerator, classe | Microsoft Docs"
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
  - "amprt/Concurrency::accelerator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "accelerator (classe)"
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
caps.latest.revision: 29
caps.handback.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# accelerator, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Un raccourci est une fonctionnalité de matériel qui est optimisée pour l’informatique parallèle de données. Un accélérateur peut être un périphérique connecté à un bus PCIe (par exemple, une carte GPU), ou il peut s’agir d’une instruction étendue définie sur l’unité centrale principale.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class accelerator;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Accelerator::Accelerator, constructeur](#accelerator__accelerator_constructor)|Initialise une nouvelle instance de la classe `accelerator`.|  
|[Accelerator :: ~ accelerator, destructeur](#accelerator___dtoraccelerator_destructor)|Détruit le `accelerator` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Accelerator::CREATE_VIEW, méthode](#accelerator__create_view_method)|Crée et retourne un `accelerator_view` objet sur cet accélérateur.|  
|[Accelerator::get_all, méthode](#accelerator__get_all_method)|Retourne un vecteur de `accelerator` objets qui représentent tous les accélérateurs disponibles.|  
|[Accelerator::get_auto_selection_view, méthode](#accelerator__get_auto_selection_view_method)|Retourne la sélection automatique de `accelerator_view`.|  
|[Accelerator::get_dedicated_memory, méthode](#accelerator__get_dedicated_memory_method)|Retourne la mémoire dédiée pour le `accelerator`, en kilo-octets.|  
|[Accelerator::get_default_cpu_access_type, méthode](#accelerator__get_default_cpu_access_type_method)|Retourne la valeur par défaut [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) pour les mémoires tampons créées sur cet accélérateur.|  
|[Accelerator::get_default_view, méthode](#accelerator__get_default_view_method)|Retourne la valeur par défaut `accelerator_view` objet auquel est associé le `accelerator`.|  
|[Accelerator::get_Description, méthode](#accelerator__get_description_method)|Retourne une courte description de le `accelerator` périphérique.|  
|[Accelerator::get_device_path, méthode](#accelerator__get_device_path_method)|Retourne le chemin d’accès de l’appareil.|  
|[Accelerator::get_has_display, méthode](#accelerator__get_has_display_method)|Détermine si le `accelerator` est attaché à un affichage.|  
|[Accelerator::get_is_debug, méthode](#accelerator__get_is_debug_method)|Détermine si le `accelerator` a la couche de DÉBOGAGE est activée pour le rapport d’erreur étendu.|  
|[Accelerator::get_is_emulated, méthode](#accelerator__get_is_emulated_method)|Détermine si le `accelerator` est émulée.|  
|[Accelerator::get_supports_cpu_shared_memory, méthode](#accelerator__get_supports_cpu_shared_memory_method)|Détermine si le `accelerator` prend en charge de la mémoire partagée|  
|[Accelerator::get_supports_double_precision, méthode](#accelerator__get_supports_double_precision_method)|Détermine si le `accelerator` est attaché à un affichage.|  
|[Accelerator::get_supports_limited_double_precision, méthode](#accelerator__get_supports_limited_double_precision_method)|Détermine si le `accelerator` prend en charge pour les fonctions mathématiques double précision limitée.|  
|[Accelerator::get_version, méthode](#accelerator__get_version_method)|Retourne la version de la `accelerator`.|  
|[Accelerator::set_default, méthode](#accelerator__set_default_method)|Retourne le chemin d’accès de l’accélérateur par défaut.|  
|[Accelerator::set_default_cpu_access_type, méthode](#accelerator__set_default_cpu_access_type_method)|Définit l’unité centrale par défaut [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) pour les tableaux et les allocations de mémoire implicites effectuées sur ce `accelerator`.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Accelerator::operator ! =, opérateur](#accelerator__operator_neq_operator)|Compare cette `accelerator` objet avec une autre et retourne `false` s’ils sont identiques ; sinon, retourne `true`.|  
|[Accelerator::operator =, opérateur](#accelerator__operator_eq_operator)|Copie le contenu de l’objet `accelerator` objet à celui-ci.|  
|[Accelerator::operator ==, opérateur](#accelerator__operator_eq_eq_operator)|Compare cette `accelerator` objet avec une autre et retourne `true` s’ils sont identiques ; sinon, retourne `false`.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Accelerator::cpu_accelerator, données membres](#accelerator__cpu_accelerator_data_member)|Obtient une chaîne constante pour le processeur `accelerator`.|  
|[Accelerator::dedicated_memory, données membres](#accelerator__dedicated_memory_data_member)|Obtient la mémoire dédiée pour le `accelerator`, en kilo-octets.|  
|[Accelerator::default_accelerator, données membres](#accelerator__default_accelerator_data_member)|Obtient une chaîne constante pour la valeur par défaut `accelerator`.|  
|[Accelerator::default_cpu_access_type, membre de données](#accelerator__default_cpu_access_type_data_member)|Obtient ou définit l’unité centrale par défaut [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) pour les tableaux et les allocations de mémoire implicites effectuées sur ce `accelerator`.|  
|[Accelerator::default_view, données membres](#accelerator__default_view_data_member)|Obtient la valeur par défaut `accelerator_view` objet auquel est associé le `accelerator`.|  
|[Accelerator::description, données membres](#accelerator__description_data_member)|Obtient une brève description de le `accelerator` périphérique.|  
|[Accelerator::device_path, données membres](#accelerator__device_path_data_member)|Obtient le chemin d’accès de l’appareil.|  
|[Accelerator::direct3d_ref, données membres](#accelerator__direct3d_ref_data_member)|Obtient une chaîne constante pour obtenir une référence Direct3D `accelerator`.|  
|[Accelerator::direct3d_warp, données membres](#accelerator__direct3d_warp_data_member)|Obtient la chaîne constante pour un [accelerator](../../../parallel/amp/reference/accelerator-class.md) de l’objet que vous pouvez utiliser pour l’exécution de code C++ AMP sur les processeurs multicœurs qui utilisent les Extensions Streaming SIMD (SSE).|  
|[Accelerator::has_display, données membres](#accelerator__has_display_data_member)|Obtient une valeur booléenne qui indique si la `accelerator` est attaché à un affichage.|  
|[Accelerator::is_debug, données membres](#accelerator__is_debug_data_member)|Indique si le `accelerator` a la couche de DÉBOGAGE est activée pour le rapport d’erreur étendu.|  
|[Accelerator::is_emulated, données membres](#accelerator__is_emulated_data_member)|Indique si la `accelerator` est émulée.|  
|[Accelerator::supports_cpu_shared_memory, membre de données](#accelerator__supports_cpu_shared_memory_data_member)|Indique si le `accelerator` prend en charge de la mémoire partagée.|  
|[Accelerator::supports_double_precision, données membres](#accelerator__supports_double_precision_data_member)|Indique si l’accélérateur prend en charge les mathématiques double précision.|  
|[Accelerator::supports_limited_double_precision, données membres](#accelerator__supports_limited_double_precision_data_member)|Indique si l’accélérateur est limitée à la prise en charge pour les fonctions mathématiques double précision.|  
|[Accelerator::version, données membres](#accelerator__version_data_member)|Obtient la version de la `accelerator`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `accelerator`  
  
## <a name="remarks"></a>Notes  
 Un raccourci est une fonctionnalité de matériel qui est optimisée pour l’informatique parallèle de données. Un raccourci est souvent un Processeur séparé, mais il peut également être une entité côté hôte virtuelle comme un périphérique DirectX REF, une CHAÎNE (un appareil côté UC est accéléré au moyen d’instructions SSE), ou que le processeur lui-même.  
  
 Vous pouvez construire une `accelerator` objet par l’énumération des périphériques disponibles, ou en obtenant le périphérique par défaut, l’appareil de référence ou le périphérique de DISTORSION.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amprt.h  
  
 **Espace de noms :** Concurrency  
  
##  <a name="a-nameacceleratordtoracceleratordestructora-acceleratoraccelerator-destructor"></a><a name="accelerator___dtoraccelerator_destructor"></a>  Accelerator :: ~ accelerator, destructeur  
 Détruit le [accelerator](../../../parallel/amp/reference/accelerator-class.md) objet.  
  
```  
~accelerator();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-nameacceleratoracceleratorconstructora-acceleratoraccelerator-constructor"></a><a name="accelerator__accelerator_constructor"></a>  Accelerator::Accelerator, constructeur  
 Initialise une nouvelle instance de la [accelerator (classe)](../../../parallel/amp/reference/accelerator-class.md).  
  
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
  
##  <a name="a-nameacceleratorcpuacceleratordatamembera-acceleratorcpuaccelerator-data-member"></a><a name="accelerator__cpu_accelerator_data_member"></a>  Accelerator::cpu_accelerator, données membres  
 Obtient une chaîne constante pour l’accélérateur CPU.  
  
```  
static const wchar_t cpu_accelerator[];  
```  
  
##  <a name="a-nameacceleratorcreateviewmethoda-acceleratorcreateview-method"></a><a name="accelerator__create_view_method"></a>  Accelerator::CREATE_VIEW, méthode  
 Crée et retourne un `accelerator_view` objet sur cet accélérateur, l’utilisation du mode de file d’attente spécifié. Lorsque le mode de file d’attente n’est pas spécifié, la nouvelle `accelerator_view` utilise le [queuing_mode::immediate](../Topic/concurrency%20namespace%20enums.md#queuing_mode) mode file d’attente.  
  
```  
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```  
  
### <a name="parameters"></a>Paramètres  
 `qmode`  
 Le mode de file d’attente.  
  
### <a name="return-value"></a>Valeur de retour  
 Un nouveau `accelerator_view` objet sur cet accélérateur, l’utilisation du mode de file d’attente spécifié.  
  
##  <a name="a-nameacceleratordedicatedmemorydatamembera-acceleratordedicatedmemory-data-member"></a><a name="accelerator__dedicated_memory_data_member"></a>  Accelerator::dedicated_memory, données membres  
 Obtient la mémoire dédiée pour le [accelerator](../../../parallel/amp/reference/accelerator-class.md), en kilo-octets.  
  
```  
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;  
```  
  
##  <a name="a-nameacceleratordefaultacceleratordatamembera-acceleratordefaultaccelerator-data-member"></a><a name="accelerator__default_accelerator_data_member"></a>  Accelerator::default_accelerator, données membres  
 Obtient une chaîne constante pour la valeur par défaut [accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
static const wchar_t default_accelerator[];  
```  
  
##  <a name="a-nameacceleratordefaultcpuaccesstypedatamembera-acceleratordefaultcpuaccesstype-data-member"></a><a name="accelerator__default_cpu_access_type_data_member"></a>  Accelerator::default_cpu_access_type, membre de données  
 La valeur par défaut processeur [access_type](../Topic/concurrency%20namespace%20enums.md#access_type) pour les tableaux et les allocations de mémoire implicites effectuées sur cette ce `accelerator`.  
  
```  
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;  
```  
  
##  <a name="a-nameacceleratordefaultviewdatamembera-acceleratordefaultview-data-member"></a><a name="accelerator__default_view_data_member"></a>  Accelerator::default_view, données membres  
 Obtient la vue d’accélérateur par défaut qui est associée à le [accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
__declspec(property(get= get_default_view)) accelerator_view default_view;  
```  
  
##  <a name="a-nameacceleratordescriptiondatamembera-acceleratordescription-data-member"></a><a name="accelerator__description_data_member"></a>  Accelerator::description, données membres  
 Obtient une brève description de le [accelerator](../../../parallel/amp/reference/accelerator-class.md) périphérique.  
  
```  
__declspec(property(get= get_description)) std::wstring description;  
```  
  
##  <a name="a-nameacceleratordevicepathdatamembera-acceleratordevicepath-data-member"></a><a name="accelerator__device_path_data_member"></a>  Accelerator::device_path, données membres  
 Obtient le chemin d’accès de l’accélérateur. Le chemin d’accès est unique sur le système.  
  
```  
__declspec(property(get= get_device_path)) std::wstring device_path;  
```  
  
##  <a name="a-nameacceleratordirect3drefdatamembera-acceleratordirect3dref-data-member"></a><a name="accelerator__direct3d_ref_data_member"></a>  Accelerator::direct3d_ref, données membres  
 Obtient une chaîne constante pour un accélérateur de référence Direct3D.  
  
```  
static const wchar_t direct3d_ref[];  
```  
  
##  <a name="a-nameacceleratordirect3dwarpdatamembera-acceleratordirect3dwarp-data-member"></a><a name="accelerator__direct3d_warp_data_member"></a>  Accelerator::direct3d_warp, données membres  
 Obtient la chaîne constante pour un [accelerator](../../../parallel/amp/reference/accelerator-class.md) de l’objet que vous pouvez utiliser pour l’exécution de votre code C++ AMP sur les processeurs multicœurs à l’aide des Extensions Streaming SIMD (SSE).  
  
```  
static const wchar_t direct3d_warp[];  
```  
  
##  <a name="a-nameacceleratorgetallmethoda-acceleratorgetall-method"></a><a name="accelerator__get_all_method"></a>  Accelerator::get_all, méthode  
 Retourne un vecteur de `accelerator` objets qui représentent tous les accélérateurs disponibles.  
  
```  
static inline std::vector<accelerator> get_all();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le vecteur d’accélérateurs disponibles  
  
##  <a name="a-nameacceleratorgetautoselectionviewmethoda-acceleratorgetautoselectionview-method"></a><a name="accelerator__get_auto_selection_view_method"></a>  Accelerator::get_auto_selection_view, méthode  
 Retourne l’accelerator_view de sélection automatique, qui une fois spécifié en tant que les résultats de la cible parallel_for_each dans la cible accelerator_view pour exécuter le noyau parallel_for_each être sélectionnés automatiquement par le runtime. À d’autres fins, l’accelerator_view retourné par cette méthode est identique à la valeur par défaut accelerator_view de l’accélérateur par défaut  
  
```  
static accelerator_view __cdecl get_auto_selection_view();
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’accelerator_view de sélection automatique.  
  
##  <a name="a-nameacceleratorgetdedicatedmemorymethoda-acceleratorgetdedicatedmemory-method"></a><a name="accelerator__get_dedicated_memory_method"></a>  Accelerator::get_dedicated_memory, méthode  
 Retourne la mémoire dédiée pour le [accelerator](../../../parallel/amp/reference/accelerator-class.md), en kilo-octets.  
  
```  
size_t get_dedicated_memory() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 La mémoire dédiée pour le `accelerator`, en kilo-octets.  
  
##  <a name="a-nameacceleratorgetdefaultcpuaccesstypemethoda-acceleratorgetdefaultcpuaccesstype-method"></a><a name="accelerator__get_default_cpu_access_type_method"></a>  Accelerator::get_default_cpu_access_type, méthode  
 Obtient l’access_type du processeur par défaut pour les mémoires tampons créées sur cet accélérateur  
  
```  
access_type get_default_cpu_access_type() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’access_type du processeur par défaut pour les mémoires tampons créées sur cet accélérateur.  
  
##  <a name="a-nameacceleratorgetdefaultviewmethoda-acceleratorgetdefaultview-method"></a><a name="accelerator__get_default_view_method"></a>  Accelerator::get_default_view, méthode  
 Retourne la valeur par défaut `accelerator_view` objet auquel est associé le [accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
accelerator_view get_default_view() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur par défaut `accelerator_view` objet auquel est associé le `accelerator`.  
  
##  <a name="a-nameacceleratorgetdescriptionmethoda-acceleratorgetdescription-method"></a><a name="accelerator__get_description_method"></a>  Accelerator::get_Description, méthode  
 Retourne une courte description de le [accelerator](../../../parallel/amp/reference/accelerator-class.md) périphérique.  
  
```  
std::wstring get_description() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une brève description de le `accelerator` périphérique.  
  
##  <a name="a-nameacceleratorgetdevicepathmethoda-acceleratorgetdevicepath-method"></a><a name="accelerator__get_device_path_method"></a>  Accelerator::get_device_path, méthode  
 Retourne le chemin d’accès de l’accélérateur. Le chemin d’accès est unique sur le système.  
  
```  
std::wstring get_device_path() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le chemin d’accès d’instance périphérique unique à l’échelle du système.  
  
##  <a name="a-nameacceleratorgethasdisplaymethoda-acceleratorgethasdisplay-method"></a><a name="accelerator__get_has_display_method"></a>  Accelerator::get_has_display, méthode  
 Retourne une valeur booléenne qui indique si le [accelerator](../../../parallel/amp/reference/accelerator-class.md) peut envoyer la sortie vers un affichage.  
  
```  
bool get_has_display() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si le `accelerator` peut envoyer la sortie vers un affichage ; sinon, `false`.  
  
##  <a name="a-nameacceleratorgetisdebugmethoda-acceleratorgetisdebug-method"></a><a name="accelerator__get_is_debug_method"></a>  Accelerator::get_is_debug, méthode  
 Détermine si le [accelerator](../../../parallel/amp/reference/accelerator-class.md) a la couche de DÉBOGAGE est activée pour le rapport d’erreur étendu.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si le `accelerator` a la couche de DÉBOGAGE est activée pour le rapport d’erreur étendu. Sinon, `false`.  
  
##  <a name="a-nameacceleratorgetisemulatedmethoda-acceleratorgetisemulated-method"></a><a name="accelerator__get_is_emulated_method"></a>  Accelerator::get_is_emulated, méthode  
 Détermine si le [accelerator](../../../parallel/amp/reference/accelerator-class.md) est émulée.  
  
```  
bool get_is_emulated() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si la `accelerator` est émulée. Sinon, `false`.  
  
##  <a name="a-nameacceleratorgetsupportscpusharedmemorymethoda-acceleratorgetsupportscpusharedmemory-method"></a><a name="accelerator__get_supports_cpu_shared_memory_method"></a>  Accelerator::get_supports_cpu_shared_memory, méthode  
 Retourne une valeur booléenne indiquant si l’accélérateur prend en charge la mémoire accessible par l’accélérateur et du processeur.  
  
```  
bool get_supports_cpu_shared_memory() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si l’accélérateur prend en charge la mémoire partagée de processeur ; dans le cas contraire, `false`.  
  
##  <a name="a-nameacceleratorgetsupportsdoubleprecisionmethoda-acceleratorgetsupportsdoubleprecision-method"></a><a name="accelerator__get_supports_double_precision_method"></a>  Accelerator::get_supports_double_precision, méthode  
 Retourne une valeur booléenne qui indique si l’accélérateur prend en charge le double mathématique de précision, y compris les fondus multiplier ajouter (FMA), division, réciproque et effectuer un cast entre `int` et `double`.  
  
```  
bool get_supports_double_precision() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si l’accélérateur prend en charge le double mathématique de précision ; dans le cas contraire, `false`.  
  
##  <a name="a-nameacceleratorgetsupportslimiteddoubleprecisionmethoda-acceleratorgetsupportslimiteddoubleprecision-method"></a><a name="accelerator__get_supports_limited_double_precision_method"></a>  Accelerator::get_supports_limited_double_precision, méthode  
 Retourne une valeur booléenne qui indique si l’accélérateur est limitée à la prise en charge pour le calcul de la précision double. Si l’accélérateur est uniquement prise en charge limitée, puis fusionné multiplier ajouter (FMA), division, réciproque et effectuer un cast entre `int` et `double` ne sont pas pris en charge.  
  
```  
bool get_supports_limited_double_precision() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si l’accélérateur a limité la prise en charge de double mathématique de précision ; dans le cas contraire, `false`.  
  
##  <a name="a-nameacceleratorgetversionmethoda-acceleratorgetversion-method"></a><a name="accelerator__get_version_method"></a>  Accelerator::get_version, méthode  
 Retourne la version de la [accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 La version de la `accelerator`.  
  
##  <a name="a-nameacceleratorhasdisplaydatamembera-acceleratorhasdisplay-data-member"></a><a name="accelerator__has_display_data_member"></a>  Accelerator::has_display, données membres  
 Obtient une valeur booléenne qui indique si le [accelerator](../../../parallel/amp/reference/accelerator-class.md) peut envoyer la sortie vers un affichage.  
  
```  
__declspec(property(get= get_has_display)) bool has_display;  
```  
  
##  <a name="a-nameacceleratorisdebugdatamembera-acceleratorisdebug-data-member"></a><a name="accelerator__is_debug_data_member"></a>  Accelerator::is_debug, données membres  
 Obtient une valeur booléenne qui indique si le [accelerator](../../../parallel/amp/reference/accelerator-class.md) a la couche de DÉBOGAGE est activée pour le rapport d’erreur étendu.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameacceleratorisemulateddatamembera-acceleratorisemulated-data-member"></a><a name="accelerator__is_emulated_data_member"></a>  Accelerator::is_emulated, données membres  
 Obtient une valeur booléenne qui indique si le [accelerator](../../../parallel/amp/reference/accelerator-class.md) est émulée.  
  
```  
__declspec(property(get= get_is_emulated)) bool is_emulated;  
```  
  
##  <a name="a-nameacceleratoroperatorneqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_neq_operator"></a>  Accelerator::operator ! =, opérateur  
 Compare cette `accelerator` objet avec une autre et retourne `false` s’ils sont identiques ; sinon, retourne `true`.  
  
```  
bool operator!= (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator` objet à comparer avec celle-ci.  
  
### <a name="return-value"></a>Valeur de retour  
 `false` Si les deux `accelerator` objets sont identiques ; sinon, `true`.  
  
##  <a name="a-nameacceleratoroperatoreqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_eq_operator"></a>  Accelerator::operator =, opérateur  
 Copie le contenu de l’objet [accelerator](../../../parallel/amp/reference/accelerator-class.md) objet à celui-ci.  
  
```  
accelerator& operator= (const accelerator& _Other);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator` objet d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à ce `accelerator` objet.  
  
##  <a name="a-nameacceleratoroperatoreqeqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_eq_eq_operator"></a>  Accelerator::operator ==, opérateur  
 Compare cette [accelerator](../../../parallel/amp/reference/accelerator-class.md) objet avec une autre et retourne `true` s’ils sont identiques ; sinon, retourne `false`.  
  
```  
bool operator== (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator` objet à comparer avec celle-ci.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si l’autre `accelerator` objet est identique à ce `accelerator` de l’objet ; sinon, `false`.  
  
##  <a name="a-nameacceleratorsetdefaultmethoda-acceleratorsetdefault-method"></a><a name="accelerator__set_default_method"></a>  Accelerator::set_default, méthode  
 Définit l’accélérateur par défaut à utiliser pour toute opération qui utilise implicitement l’accélérateur par défaut. Cette méthode ne réussit que si l’accélérateur par défaut sélectionné de runtime n’a pas déjà été utilisé dans une opération qui utilise implicitement l’accélérateur par défaut  
  
```  
static inline bool set_default(std::wstring _Path);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Path`  
 Le chemin d’accès à l’accélérateur.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si l’appel aboutit à la définition de l’accélérateur par défaut. Sinon, `false`.  
  
##  <a name="a-nameacceleratorsetdefaultcpuaccesstypemethoda-acceleratorsetdefaultcpuaccesstype-method"></a><a name="accelerator__set_default_cpu_access_type_method"></a>  Accelerator::set_default_cpu_access_type, méthode  
 Définissez l’access_type du processeur par défaut pour les tableaux créés sur cet accélérateur ou des allocations de mémoire implicites comme partie d’array_views accessible sur ce cet accélérateur. Cette méthode ne réussit que si la default_cpu_access_type pour l’accélérateur n’a pas encore été remplacé par un appel précédent à cette méthode et le default_cpu_access_type d’exécution sélectionnée pour cet accélérateur n’a pas encore été utilisé pour allouer un tableau ou d’une allocation de mémoire implicites sauvegarde un array_view accédé sur cet accélérateur.  
  
```  
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Default_cpu_access_type`  
 L’access_type du processeur par défaut à utiliser pour les allocations de mémoire tableau/array_view sur cet accélérateur.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur booléenne indiquant si l’access_type du processeur par défaut pour l’accélérateur a été correctement définie.  
  
##  <a name="a-nameacceleratorsupportscpusharedmemorydatamembera-acceleratorsupportscpusharedmemory-data-member"></a><a name="accelerator__supports_cpu_shared_memory_data_member"></a>  Accelerator::supports_cpu_shared_memory, membre de données  
 Obtient une valeur booléenne indiquant si le `accelerator` prend en charge de la mémoire partagée.  
  
```  
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;  
```  
  
##  <a name="a-nameacceleratorsupportsdoubleprecisiondatamembera-acceleratorsupportsdoubleprecision-data-member"></a><a name="accelerator__supports_double_precision_data_member"></a>  Accelerator::supports_double_precision, données membres  
 Obtient une valeur booléenne qui indique si l’accélérateur prend en charge les mathématiques double précision.  
  
```  
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;  
```  
  
##  <a name="a-nameacceleratorsupportslimiteddoubleprecisiondatamembera-acceleratorsupportslimiteddoubleprecision-data-member"></a><a name="accelerator__supports_limited_double_precision_data_member"></a>  Accelerator::supports_limited_double_precision, données membres  
 Obtient une valeur booléenne qui indique si l’accélérateur est limitée à la prise en charge pour le calcul de la précision double. Si l’accélérateur est uniquement prise en charge limitée, puis fusionné multiplier ajouter (FMA), division, réciproque et effectuer un cast entre `int` et `double` ne sont pas pris en charge.  
  
```  
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;  
```  
  
##  <a name="a-nameacceleratorversiondatamembera-acceleratorversion-data-member"></a><a name="accelerator__version_data_member"></a>  Accelerator::version, données membres  
 Obtient la version de la [accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="a-nameacceleratorviewdtoracceleratorviewdestructora-acceleratorviewacceleratorview-destructor"></a><a name="accelerator_view___dtoraccelerator_view_destructor"></a>  accelerator_view :: ~ accelerator_view, destructeur  
 Détruit le [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet.  
  
```  
~accelerator_view();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-nameacceleratorviewacceleratordatamembera-acceleratorviewaccelerator-data-member"></a><a name="accelerator_view__accelerator_data_member"></a>  accelerator_view::Accelerator, données membres  
 Obtient le [accelerator](../../../parallel/amp/reference/accelerator-class.md) de l’objet pour le [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet.  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
##  <a name="a-nameacceleratorviewacceleratorviewconstructora-acceleratorviewacceleratorview-constructor"></a><a name="accelerator_view__accelerator_view_constructor"></a>  accelerator_view::accelerator_view, constructeur  
 Initialise une nouvelle instance de la [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) classe en copiant une existante `accelerator_view` objet.  
  
```  
accelerator_view(const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator_view` objet à copier.  
  
##  <a name="a-nameacceleratorviewcreatemarkermethoda-acceleratorviewcreatemarker-method"></a><a name="accelerator_view__create_marker_method"></a>  accelerator_view::create_marker, méthode  
 Retourne un futur pour effectuer le suivi de l’achèvement de toutes les commandes envoyées jusqu'à présent à ce `accelerator_view` objet.  
  
```  
concurrency::completion_future create_marker();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un futur pour effectuer le suivi de l’achèvement de toutes les commandes envoyées jusqu'à présent à ce `accelerator_view` objet.  
  
##  <a name="a-nameacceleratorviewflushmethoda-acceleratorviewflush-method"></a><a name="accelerator_view__flush_method"></a>  accelerator_view::Flush, méthode  
 Envoie toutes les commandes en attente en attente pour le [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet à l’accélérateur pour l’exécution.  
  
```  
void flush();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `void`.  
  
##  <a name="a-nameacceleratorviewgetacceleratormethoda-acceleratorviewgetaccelerator-method"></a><a name="accelerator_view__get_accelerator_method"></a>  accelerator_view::get_accelerator, méthode  
 Retourne le [accelerator](../../../parallel/amp/reference/accelerator-class.md) de l’objet pour le [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet.  
  
```  
accelerator get_accelerator() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le `accelerator` de l’objet pour le `accelerator_view` objet.  
  
##  <a name="a-nameacceleratorviewgetisautoselectionmethoda-acceleratorviewgetisautoselection-method"></a><a name="accelerator_view__get_is_auto_selection_method"></a>  accelerator_view::get_is_auto_selection, méthode  
 Retourne une valeur booléenne qui indique si le runtime sélectionne automatiquement un accélérateur approprié lorsque l’accelerator_view est transmis à un [parallel_for_each](../Topic/concurrency%20namespace%20functions.md#parallel_for_each).  
  
```  
bool get_is_auto_selection() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` Si le runtime va sélectionner automatiquement un accélérateur approprié ; dans le cas contraire, `false`.  
  
##  <a name="a-nameacceleratorviewgetisdebugmethoda-acceleratorviewgetisdebug-method"></a><a name="accelerator_view__get_is_debug_method"></a>  accelerator_view::get_is_debug, méthode  
 Retourne une valeur booléenne qui indique si le [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet a la couche de DÉBOGAGE est activée pour le rapport d’erreur étendu.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur booléenne qui indique si le `accelerator_view` objet a la couche de DÉBOGAGE est activée pour le rapport d’erreur étendu.  
  
##  <a name="a-nameacceleratorviewgetqueuingmodemethoda-acceleratorviewgetqueuingmode-method"></a><a name="accelerator_view__get_queuing_mode_method"></a>  accelerator_view::get_queuing_mode, méthode  
 Retourne le mode file d’attente pour le [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet.  
  
```  
queuing_mode get_queuing_mode() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le mode de file d’attente pour le `accelerator_view` objet.  
  
##  <a name="a-nameacceleratorviewgetversionmethoda-acceleratorviewgetversion-method"></a><a name="accelerator_view__get_version_method"></a>  accelerator_view::get_version, méthode  
 Retourne la version de la [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md).  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 La version de la `accelerator_view`.  
  
##  <a name="a-nameacceleratorviewisautoselectiondatamembera-acceleratorviewisautoselection-data-member"></a><a name="accelerator_view__is_auto_selection_data_member"></a>  accelerator_view::is_auto_selection, membre de données  
 Obtient une valeur booléenne qui indique si le runtime sélectionne automatiquement un accélérateur approprié lorsque l’accelerator_view est transmis à un [parallel_for_each](concurrency%20namespace%20functions.md#parallel_for_each).  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
##  <a name="a-nameacceleratorviewisdebugdatamembera-acceleratorviewisdebug-data-member"></a><a name="accelerator_view__is_debug_data_member"></a>  accelerator_view::is_debug, données membres  
 Obtient une valeur booléenne qui indique si le [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet a la couche de DÉBOGAGE est activée pour le rapport d’erreur étendu.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameacceleratorviewoperatorneqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_neq_operator"></a>  accelerator_view::operator ! =, opérateur  
 Compare cette [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet avec une autre et retourne `false` s’ils sont identiques ; sinon, retourne `true`.  
  
```  
bool operator!= (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator_view` objet à comparer avec celle-ci.  
  
### <a name="return-value"></a>Valeur de retour  
 `false` si les deux objets sont identiques ; sinon, `true`.  
  
##  <a name="a-nameacceleratorviewoperatoreqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_eq_operator"></a>  accelerator_view::operator =, opérateur  
 Copie le contenu de l’objet [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet dans celui-ci.  
  
```  
accelerator_view& operator= (const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator_view` objet d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à la modification `accelerator_view` objet.  
  
##  <a name="a-nameacceleratorviewoperatoreqeqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_eq_eq_operator"></a>  accelerator_view::operator ==, opérateur  
 Compare cette [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet avec une autre et retourne `true` s’ils sont identiques ; sinon, retourne `false`.  
  
```  
bool operator== (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator_view` objet à comparer avec celle-ci.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si les deux objets sont identiques ; sinon, `false`.  
  
##  <a name="a-nameacceleratorviewqueuingmodedatamembera-acceleratorviewqueuingmode-data-member"></a><a name="accelerator_view__queuing_mode_data_member"></a>  accelerator_view::queuing_mode, données membres  
 Obtient le mode de file d’attente pour le [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet.  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
##  <a name="a-nameacceleratorviewversiondatamembera-acceleratorviewversion-data-member"></a><a name="accelerator_view__version_data_member"></a>  accelerator_view::version, données membres  
 Obtient la version de la [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md).  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="a-nameacceleratorviewwaitmethoda-acceleratorviewwait-method"></a><a name="accelerator_view__wait_method"></a>  accelerator_view::wait, méthode  
 Attend que toutes les commandes envoyées à la [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet se termine.  
  
```  
void wait();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `void`.  
  
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace (C++ AMP)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)

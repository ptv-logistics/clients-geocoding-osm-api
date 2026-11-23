# PlacesApi

All URIs are relative to *https://api.myptv.com/geocoding-osm/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**searchPlacesByAddress**](PlacesApi.md#searchplacesbyaddress) | **GET** /places/by-address |  |
| [**searchPlacesByPosition**](PlacesApi.md#searchplacesbyposition) | **GET** /places/by-position/{latitude}/{longitude} |  |
| [**searchPlacesByText**](PlacesApi.md#searchplacesbytext) | **GET** /places/by-text |  |



## searchPlacesByAddress

> PlacesSearchResult searchPlacesByAddress(country, state, province, locality, postalCode, street, houseNumber, languages)



Searches for places based on a multi-field address input.

### Example

```ts
import {
  Configuration,
  PlacesApi,
} from '';
import type { SearchPlacesByAddressRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new PlacesApi(config);

  const body = {
    // string | The country in which the places should be searched. A country may be defined by name or ISO code (ISO 3166-1 alpha-2). (optional)
    country: country_example,
    // string | A subdivision of a country, for example a state or a region. Using this field narrows down the search and reduces the number of possible results. (optional)
    state: state_example,
    // string | A subdivision of a state, for example the province or county. Using this field narrows down the search and reduces the number of possible results. (optional)
    province: province_example,
    // string | The locality of the address, which may be a city, a district or subdistrict. (optional)
    locality: locality_example,
    // string | The postal code, or zip-code, which is used by a postal authority of a country to identify where the address is located. (optional)
    postalCode: postalCode_example,
    // string | The name of the road where the address is located. It may contain a house number, but using the **houseNumber** field instead will lead to better results. (optional)
    street: street_example,
    // string | The house number of the address. (optional)
    houseNumber: houseNumber_example,
    // Array<string> | A comma-separated list of preferred languages for the response, formatted according to [ISO-639-1](https://www.loc.gov/standards/iso639-2/php/code_list.php) for languages or [BCP47](https://tools.ietf.org/html/bcp47) for language variants. These languages are ordered by decreasing priority. In case none of the given preferred languages is available in the data, the default language is used, which is the language spoken in the country or region of the result (optional)
    languages: ["de","en"],
  } satisfies SearchPlacesByAddressRequest;

  try {
    const data = await api.searchPlacesByAddress(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **country** | `string` | The country in which the places should be searched. A country may be defined by name or ISO code (ISO 3166-1 alpha-2). | [Optional] [Defaults to `undefined`] |
| **state** | `string` | A subdivision of a country, for example a state or a region. Using this field narrows down the search and reduces the number of possible results. | [Optional] [Defaults to `undefined`] |
| **province** | `string` | A subdivision of a state, for example the province or county. Using this field narrows down the search and reduces the number of possible results. | [Optional] [Defaults to `undefined`] |
| **locality** | `string` | The locality of the address, which may be a city, a district or subdistrict. | [Optional] [Defaults to `undefined`] |
| **postalCode** | `string` | The postal code, or zip-code, which is used by a postal authority of a country to identify where the address is located. | [Optional] [Defaults to `undefined`] |
| **street** | `string` | The name of the road where the address is located. It may contain a house number, but using the **houseNumber** field instead will lead to better results. | [Optional] [Defaults to `undefined`] |
| **houseNumber** | `string` | The house number of the address. | [Optional] [Defaults to `undefined`] |
| **languages** | `Array<string>` | A comma-separated list of preferred languages for the response, formatted according to [ISO-639-1](https://www.loc.gov/standards/iso639-2/php/code_list.php) for languages or [BCP47](https://tools.ietf.org/html/bcp47) for language variants. These languages are ordered by decreasing priority. In case none of the given preferred languages is available in the data, the default language is used, which is the language spoken in the country or region of the result | [Optional] |

### Return type

[**PlacesSearchResult**](PlacesSearchResult.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## searchPlacesByPosition

> PlacesSearchResult searchPlacesByPosition(latitude, longitude, detailLevel, languages)



Searches for places near a given geographical position.

### Example

```ts
import {
  Configuration,
  PlacesApi,
} from '';
import type { SearchPlacesByPositionRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new PlacesApi(config);

  const body = {
    // number
    latitude: 1.2,
    // number
    longitude: 1.2,
    // DetailLevel | Detail level of the address. (optional)
    detailLevel: ...,
    // Array<string> | A comma-separated list of preferred languages for the response, formatted according to [ISO-639-1](https://www.loc.gov/standards/iso639-2/php/code_list.php) for languages or [BCP47](https://tools.ietf.org/html/bcp47) for language variants. These languages are ordered by decreasing priority. In case none of the given preferred languages is available in the data, the default language is used, which is the language spoken in the country or region of the result (optional)
    languages: ["de","en"],
  } satisfies SearchPlacesByPositionRequest;

  try {
    const data = await api.searchPlacesByPosition(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **latitude** | `number` |  | [Defaults to `undefined`] |
| **longitude** | `number` |  | [Defaults to `undefined`] |
| **detailLevel** | `DetailLevel` | Detail level of the address. | [Optional] [Defaults to `undefined`] [Enum: COUNTRY, STATE, PROVINCE, CITY, SUBURB, MAJOR_STREETS, MAJOR_AND_MINOR_STREETS, BUILDING] |
| **languages** | `Array<string>` | A comma-separated list of preferred languages for the response, formatted according to [ISO-639-1](https://www.loc.gov/standards/iso639-2/php/code_list.php) for languages or [BCP47](https://tools.ietf.org/html/bcp47) for language variants. These languages are ordered by decreasing priority. In case none of the given preferred languages is available in the data, the default language is used, which is the language spoken in the country or region of the result | [Optional] |

### Return type

[**PlacesSearchResult**](PlacesSearchResult.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## searchPlacesByText

> PlacesSearchResult searchPlacesByText(searchText, languages)



Searches for places based on a single-field text input.

### Example

```ts
import {
  Configuration,
  PlacesApi,
} from '';
import type { SearchPlacesByTextRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new PlacesApi(config);

  const body = {
    // string | Free-form text input that describes a place.
    searchText: searchText_example,
    // Array<string> | A comma-separated list of preferred languages for the response, formatted according to [ISO-639-1](https://www.loc.gov/standards/iso639-2/php/code_list.php) for languages or [BCP47](https://tools.ietf.org/html/bcp47) for language variants. These languages are ordered by decreasing priority. In case none of the given preferred languages is available in the data, the default language is used, which is the language spoken in the country or region of the result (optional)
    languages: ["de","en"],
  } satisfies SearchPlacesByTextRequest;

  try {
    const data = await api.searchPlacesByText(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **searchText** | `string` | Free-form text input that describes a place. | [Defaults to `undefined`] |
| **languages** | `Array<string>` | A comma-separated list of preferred languages for the response, formatted according to [ISO-639-1](https://www.loc.gov/standards/iso639-2/php/code_list.php) for languages or [BCP47](https://tools.ietf.org/html/bcp47) for language variants. These languages are ordered by decreasing priority. In case none of the given preferred languages is available in the data, the default language is used, which is the language spoken in the country or region of the result | [Optional] |

### Return type

[**PlacesSearchResult**](PlacesSearchResult.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


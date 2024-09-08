# Insomnia Test Cases For API Security Headers

This repository contains a list of Insomnia test cases to validate HTTP Security Headers which are mandated to be part of the API responses as well as a number of security headers which should be removed from the API responses. 

## Usage

In order to make maximum out of this, the following is the correct way of configuring it. 

1. Open Insomnia.
2. Create a New Documentation.
3. Select the APIs/Insomnia Collection.
4. Go to Tests.
5. Configure the below test cases. 
6. Run them across all APIs. 

## Test Cases

The HTTP Headers which are validated are as below. 

1. X-Frame-Options Header

```
const response = await insomnia.send();

const headers = response.headers;

const xFrameOptions = headers['x-frame-options'];

if (xFrameOptions) {

  if (xFrameOptions === 'DENY') {

    console.log('X-Frame-Options header is set to DENY');

  } else if (xFrameOptions === 'SAMEORIGIN') {

    console.log('X-Frame-Options header is set to SAMEORIGIN');

  } else {

    console.log(`X-Frame-Options header has an unexpected value: ${xFrameOptions}`);
  }

} else {

  throw new Error('X-Frame-Options header is missing');

}
```

## 2. Strict Transport Security Header

```
const response = await insomnia.send();

const headers = response.headers;

const hsts = headers['strict-transport-security'];

if (hsts) {

  if (hsts) {

    console.log('Strict-Transport-Security header is set');

  } else {

    console.log('Strict-Transport-Security not-set');

  }
} else {

  throw new Error('Strict Transport Security Header is missing');

}


```

## 3. X-Content-Type Options Header

```
const response = await insomnia.send();

const headers = response.headers;

const xcto = headers['x-content-type-options'];

if (xcto) {

  if (xcto === 'nosniff') {

    console.log('X-Content-Type header is set to nosniff');

  }  else {

    console.log(`X-Content-Type header has an unexpected value: ${xcto}`);
  }

} else {

  throw new Error('X-Content-Type header is missing');

}

```

## 4. X-XSS-Protection Header

```
const response = await insomnia.send();

const headers = response.headers;

const xxssprotect = headers['x-xss-protection'];

if (xxssprotect) {
  
  if (xxssprotect) {

    console.log('X-XSS-Protection header is set');

  } else {

    console.log('X-XSS-Protection not-set');

  }

} else {

  throw new Error('X-XSS-Protection is missing');
  
}

```


## 5. Cache Control Header

```
const response = await insomnia.send();

const headers = response.headers;

const cacheControl = headers['cache-control'];

if (cacheControl) {
  
  if (cacheControl) {

    console.log('Cache-Control header is set');

  } else {

    console.log('Cache-Control not-set');

  }

} else {

  throw new Error('Cache-Control is missing');
  
}

```

## 6. Server Header

```
const response = await insomnia.send();

const headers = response.headers;

const serverHeader = headers['server'];

if (serverHeader) {

  if (serverHeader) {

    throw new Error('Server Header is set - Remove It!');

  } else if (serverHeader) {

    console.log('Server Header is not set');

} else {

  throw new Error('X-Frame-Options header is missing');

}
}
```

## 7. X-Powered-By Header

```
const response = await insomnia.send();

const headers = response.headers;

const xpwdby = headers['x-powered-by'];

if (xpwdby) {

  if (xpwdby) {

    throw new Error('X-Powered-By Header is set - Remove It!');

  } else if (xpwdby) {

    console.log('X-Powered-By Header is not set');

} else {

  throw new Error('X-Powered-By Header header is missing');

}
}
```

## 8. X-AspNet-Version Header

```
const response = await insomnia.send();

const headers = response.headers;

const xaspnet = headers['x-aspnet-version'];

if (xaspnet) {

  if (xaspnet) {

    throw new Error('X-AspNet-Version Header is set - Remove It!');

  } else if (xaspnet) {

    console.log('X-AspNet-Version Header is not set');

} else {

  throw new Error('X-AspNet-Version Header header is missing');

}
}
```

## 9. X-AspNetMvc-Version Header

```
const response = await insomnia.send();

const headers = response.headers;

const xaspnet = headers['x-aspnetmvc-version'];

if (xaspnet) {

  if (xaspnet) {

    throw new Error('X-AspNetMvc-Version Header is set - Remove It!');

  } else if (xaspnet) {

    console.log('X-AspNetMvc-Version Header is not set');

} else {

  throw new Error('X-AspNetMvc-Version Header header is missing');

}
}
```

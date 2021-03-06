# Downgrade module

Weex downgrade to web module. Version should be semver format.

## install

install from npm command: `npm install @weex-project/downgrade --save`

## sample

```js
import Downgrade from '@weex-project/downgrade'

// force downgrade
Downgrade.force()

/*
    check condition. When match anyone condition will return downgrade is true. return format as below:
    {
        isDowngrade: true,
        errorType: 1,
        code: 1000,
        errorMessage: 'XXXXXXXX'
    }
*/
Downgrade.check({
    ios: {
        osVersion: '>1.0',
        appVersion: '>1.0.0',
        weexVersion: '>1',
        deviceModel: ['iPhone5,1']
    },
    android: {
        osVersion: '>1.0',
        appVersion: '>1.0.0',
        weexVersion: '>1',
        deviceModel: ['G-2PW2100']
    }
})

// check condition with multiple app. The `MY_APP_A` is WXEnvironment's appName param.
Downgrade.check({
    ios: {
        osVersion: '>1.0',
        appVersion: {
            MY_APP_A: '>1.0.0',
            MY_APP_B: '>2.0.0'
        },
        weexVersion: '>1',
        deviceModel: ['iPhone5,1']
    },
    android: {
        osVersion: '>1.0',
        appVersion: {
            MY_APP_A: '>1.0.0',
            MY_APP_C: '>3.0.0'
        },
        weexVersion: '>1',
        deviceModel: ['G-2PW2100']
    }
})

// When match condition will auto downgrade to web
Downgrade.condition({
    ios: {
        osVersion: '>1.0',
        appVersion: '>1.0.0',
        weexVersion: '>1',
        deviceModel: ['iPhone5,1']
    },
    android: {
        osVersion: '>1.0',
        appVersion: '>1.0.0',
        weexVersion: '>1',
        deviceModel: ['G-2PW2100']
    }
})

// When condition with multiple app. The `MY_APP_A` is WXEnvironment's appName param.
Downgrade.condition({
    ios: {
        osVersion: '>1.0',
        appVersion: {
            MY_APP_A: '>1.0.0',
            MY_APP_B: '>2.0.0'
        },
        weexVersion: '>1',
        deviceModel: ['iPhone5,1']
    },
    android: {
        osVersion: '>1.0',
        appVersion: {
            MY_APP_A: '>1.0.0',
            MY_APP_C: '>3.0.0'
        },
        weexVersion: '>1',
        deviceModel: ['G-2PW2100']
    }
})
```

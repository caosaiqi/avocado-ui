---
nav:
  title: 组件
  path: /components
group:
  title: Form 表单
---
# Form 表单
## 代码演示

```tsx
/**
 * title: 基本
 * desc: 精简版Formik
 */
import * as React from 'react';
import {  Alayout, Ainput, Aform, Button } from 'fbm-ui'

const formProps = {
  initialValues: {
    name: '',
    password: '',
  },
  validate: (values, props) => {
    const errors = {};
    const helperTexts = {
      name: '请输入名称',
      password: '请输入密码',
    }
    Object.keys(helperTexts).forEach(k => {
      if (values[k] === '') {
        errors[k] = helperTexts[k]
      }
    })
    return errors
  }, 
}

export default () => (
  <Alayout>
    <Aform {...formProps}>
      <Ainput label="名称" name="name" sx={{mr: 2}} />
      <br/>
      <Ainput label="密码" name="password" />
       <br/>
      <Button sx={{m: '3px 0px 0 5px'}} variant="contained"  type="submit">
        提交
      </Button>
    </Aform>
  </Alayout>
)

```

<API></API>
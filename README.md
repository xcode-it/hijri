# @get-x/hijri

> This is a modified version of moment-jalaali by Behrang Noruzi Niya and extends Suhail Alkowaileet's work on moment-hijri.js lib

## Install

```bash
npm install --save @get-x/hijri
```

## Usage

```jsx
import React from 'react'
import moment from '@get-x/hijri'

export default function HijriTable() {
    return (
        <table>
            <thead>
              <tr>
                <td>Date in Hijri</td>
                <td>Month Name/Number</td>
                <td>Hijri to Gregorian</td>
                <td>Month Name/Number</td>
                <td>strict parsing</td>
              </tr>
            </thead>
            {[6, 7, 8, 9, 10, 11, 12, 1, 2, 3, 4, 5].map((x) => {
                const date = moment(`1444-${x}-08`, 'iYYYY-iM-iD', false)
                const strict = moment(`1444-${x}-08`, 'iYYYY-iM-iD', true)
                const fH = date.format('iDD-iMM-iYYYY')
                const fG = date.format('DD-MMMM-YYYY')
                const ffH = moment(date).format('iMMMM')
                const sffG = moment(strict).format('MMMM')
                return (
                  <tbody key={x}>
                    <tr>
                        <td>{fH}</td>
                        <td>{ffH}</td>
                        <td>{fG}</td>
                        <td>{sffG}</td>
                        <td>false / true</td>
                    </tr>
                  </tbody>
                )
            })}
            {[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12].map((x) => {
                const date = moment(`01-${x}-1990`, 'D-M-YYYY', false)
                const strict = moment(`01-${x}-1990`, 'D-M-YYYY', true)
                const fH = date.format('iDD-iMMMM-iYYYY')
                const fG = date.format('DD-MMMM-YYYY')
                const sffH = moment(strict).format('iMM')
                const ffG = moment(date).format('MM')
                return (
                  <tbody key={x}>
                      <tr>
                          <td>{fH}</td>
                          <td>{sffH}</td>
                          <td>{fG}</td>
                          <td>{ffG}</td>
                          <td>true / false</td>
                      </tr>
                  </tbody>
                )
            })}
        </table>
    )
}

```

```js
var moment = require('@get-x/hijri')

const hijriDate = moment(`1424-12-17`, 'iYYYY-iM-iD', true)
const gregorianDate = moment(`1990-07-09`, 'YYYY-M-D', true)
console.log("Hijri Format", gregorianDate.format('iDD-iMM-iYYYY'))
console.log("Gregoria Format", hijriDate.format('DD-MM-YYYY'))

// node .\index.js
// Hijri Format ١٧-١٢-١٤١٠
// Gregoria Format ٠٨-٠٢-٢٠٠٤

```

## License

GIT © [phantom-x](https://github.com/phantom-x/hijri)
NPM © [@get-x/hijri](https://www.npmjs.com/package/@get-x/hijri)

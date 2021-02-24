# Aikamoista Jos tää toimii

Tähän vaan sitten tekstiä ja tarinaa.

```c#
[Route("addFieldToCard")]
        [HttpPost]
        //In use PWA
        public async Task<IHttpActionResult> AddFieldToCard()
        {
            try
            {
                ArtturiPrincipalModel usermodel = (User as ArtturiPrincipal).ArtturiPrincipalModel;

                HttpContent content = Request.Content;
                string jsonContent = content.ReadAsStringAsync().Result;
                kkenttaDTO kkentta = JsonConvert.DeserializeObject<kkenttaDTO>(jsonContent);

                var (success, message, model) = await _cardService.AddFieldToCard(kkentta, usermodel.Username, usermodel.DefaultPlace);

                return Ok(new { success, message, model });
            }
            catch (Exception ex)
            {

                new LogDataHandler().LogError(ex);
                return InternalServerError(ex.InnerException);
            }
        }

```

## Tuosta pikkanen koodi pläjäys mikä on maailman mahtavin
Tässä JavaScript väreillä:
```js
methods:  {

forceMapRerender:  function  forceMapRerender()  {

this.mapKey +=  1;

},

zoomUpdate:  function  zoomUpdate(zoom)  {

this.currentZoom = zoom;

},

centerUpdate:  function  centerUpdate(center)  {

this.currentCenter = center;

},

innerClick:  function  innerClick()  {

alert('Click!');

},

centerStart:  function  centerStart()  {

// This.$refs.myMap.mapObject.panTo(this.startWithPopup).fitBounds(this.startWithPopup.toBounds(1000));

this.$refs.myMap.mapObject.flyTo(this.startWithPopup,  15);

this.currentCenter =  this.startWithPopup;

},

centerEnd:  function  centerEnd()  {

// This.$refs.myMap.mapObject.panTo(this.endWithTooltip).fitBounds(this.endWithTooltip.toBounds(1000));

this.$refs.myMap.mapObject.flyTo(this.endWithTooltip,  15);

this.currentCenter =  this.endWithTooltip;

}

}

});
```
Tässä hieman Vue.js värillisenä:

```js
<script>

  

import  { mapState, mapActions }  from  'vuex'

import router from  '../router/index'

import  { WorkService }  from  '../services/api.service'

import  { common }  from  '../utils/common'

import WorkList from  '../components/worksearch/work-list-html'

  

export  default  {

components:  {

WorkList

},

props:  {

// Base 64 encoded

search:  {

type:  String,

required:  true

}

},

  

data()  {

return  {

common,

workOrders: [],

searchParameters:  {},

loadingMoreMobilePages:  false,

}

},
```



### Tästä sitten pikkasen parempia fotoja

Linkki aneon sivuille [Aneo](www.aneo.fi) 
**==Perkules==**
![Metukkaa](https://is.mediadelivery.fi/img/658/4cc35d6c46bd422bb1408457f62c9b48.jpg.webp)

Mentula | Rahkaa
---------- | -------
Ostaa | Vai ei osta
Grillattuna | Vai raakana

- [x] Ostaa se rahkaa
- [ ] Ei osta rahkaa
- [ ] Paljon rahkaa


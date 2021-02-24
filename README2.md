# Aikamoista Jos tää toimii

Tähän vaan sitten tekstiä ja tarinaa.

```C#
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


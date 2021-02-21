<template>
  <div id="app">
    <nav class="navbar navbar-dark bg-dark">
      <div id="nav">
        <router-link to="/">
          <b-icon
            icon="basket"
            style="width: 50px; height: 30px"
          ></b-icon>
        </router-link>
        |
        <router-link to="/about">Product</router-link>
      </div>
      <div>
        <router-link to="/User">
          <button
            type="button "
            class="btn btn-outline-success mr-1"
            @click="submit()"
          >
            confirm
          </button>
          <button
            type="button"
            class="btn btn-outline-danger"
            @click="cleardata()"
          >
            Clear
          </button>
        </router-link>
      </div>
    </nav>
    <router-view
      :Total="Total"
      :User="User"
      :Menuitem="Menuitem"
      :Data="Data"
      @Order="menuorder"
      @OrderAdmin="AddMenu"
    />
  </div>
</template>
<script>
export default {
  data() {
    return {
      Total: 0,
      Menuitem: [
        {
          NameProduct: "Kagarino kirie",
          img:
            "https://cf.shopee.co.th/file/7a54c57143ce524785ee6e5f21610e59",
          Price: 2365
        },
        {
          NameProduct: "Hatsune Miku",
          img:
            "https://i.pinimg.com/564x/53/47/b0/5347b0235f8003cc9740c061bd02bfb5.jpg",
          Price: 3999
        },
        {
          NameProduct: "Ram",
          img:
            "https://fk.lnwfile.com/_/fk/_raw/2a/ov/wx.jpg",
          Price: 1090
        },
        {
          NameProduct: "Rem",
          img:
            "https://images.goodsmile.info/cgm/images/product/20170630/6550/46224/large/e9b34018d19d82d517e8d8e330040ff8.jpg",
          Price: 1080
        },
        {
          NameProduct: "Boa Hancock",
          img:
            "https://www.hobbyfanclub.com/web/board/2020/5b3ijlihfqnceyzk1nzp2422020650272211.jpg",
          Price: 4400
        },
        {
          NameProduct: "Muzan",
          img:
            "https://hobbyfanclub.com/web/board/2021/apg2m5v1ryem0yohwjwi2122021231456806.jpg",
          Price: 3699
        },
        {
          NameProduct: "Grand Order Saber",
          img:
            "https://i.pinimg.com/originals/ec/1f/80/ec1f800e8daba4c64e53153b81c8068d.jpg",
          Price: 4900
        },
        {
          NameProduct: "Shinobu Kocho",
          img:
            "https://1.bp.blogspot.com/-m04p8BJJM2I/Xz-qDvgKV1I/AAAAAAABqC4/e-KxuGhBCnEt8bIn3SYItPeXarNZtiHogCLcBGAsYHQ/s1600/107109.jpg",
          Price: 4826
        },
        {
          NameProduct: "Tokisaki Kurumi",
          img:
            "https://fu.lnwfile.com/d11dzc.jpg",
          Price: 7090
        },
        {
          NameProduct: "Zoro",
          img:
            "https://cf.shopee.co.th/file/2e7086873f36030069dd04ded4395d3b",
          Price: 4500
        },
        {
          NameProduct: "Zhen Ji King of Glory",
          img:
            "https://i.pinimg.com/564x/c1/f3/ad/c1f3ad32ee19924548b23e3d94fcecfd.jpg",
          Price: 4800
        },
        {
          NameProduct: "Nezuko",
          img:
            "https://ae01.alicdn.com/kf/H717124f2ef5147c58006c5a7d8754cbcC/Aniplex-ARTFX-J-Demon-Slayer-Kamado-Nezuko-PVC-Action-Figure-Anime-Figure-Model-Toys-Collection-Doll.jpg",
          Price: 3899
        }
      ],
      select: [],
      Data: []
    }
  },
  methods: {
    //คิดเงินรวมทั้งหมด
    submit() {
      this.Data = this.select;
      this.Total = 0;
      for (var i = 0; i < this.Data.length; i++) {
        this.Total = this.Total + this.Data[i].Total;
      }
    },
    cleardata() {
      this.Total = 0;
      this.Data = [{}];
      this.select = [{}];
    },
    menuorder(value) {
      this.select = value;
    },
    AddMenu(value) {
      this.Menuitem.push(value);
    }
  }
};
</script>

<style>


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #e637dd;
}

#nav {
  padding: 10px;
}

#nav a {
  font-weight: bold;
  color: #ecd25d;
}

#nav a.router-link-exact-active {
  color: #1bc2b4;
}
</style>

<template>
  <div id="post_detail_page">
    <div>
      <h1 class="post_title text-2xl font-bold mb-[2px]">
        Chứng chỉ PTE là gì?
      </h1>
      <div class="post_meta text-[11px] text-gray-400">
        <span class="post_time">Cập nhật lúc: 16:12 12/12/2021</span> -
        <span class="post_author">
          Nguyễn Văn A
        </span>
      </div>
    </div>

    <div class="post_content mt-[10px]" v-html="postData.content"/>

    <div class="post-tags mt-5 mb-5 flex gap-[5px] flex-wrap">
      <span class="font-bold">Tags:</span>
      <RouterLink
          :to="`/tags/` + tag.slug"
          :key="tag.slug + Math.round()"
          v-for="tag in postData.postTags"
      >
        <a-tag class="mt-1 hover:text-gray-400"
               :color="tagColors[Math.round(Math.random() * tagColors.length)]"
        >
          #{{ tag.name }}
        </a-tag>
      </RouterLink>
    </div>

    <div class="next_prev_post flex p-[20px]">
      <div class="prev_post w-1/2 flex gap-[5px]">
        <img class="h-[67px] w-[54px]"
             src="https://thepte.com/wp-content/uploads/2021/06/free-PTE-mock-test-300x300.jpg.webp">
        <div class="prev_post_title p-[5px]">
          <p class="font-bold text-gray-400 text-[11px] text-center">
            <swap-left-outlined/>
            Bài viết trước
          </p>
          <a href="https://thepte.com/pte-mock-test-1/">PTE Mock Test 1</a>
        </div>
      </div>

      <div class="next_post w-1/2 flex">
        <img class="h-[67px] w-[54px] "
             src="https://thepte.com/wp-content/uploads/2021/06/PTE-fill-in-the-blanks-without-cheating-1-300x300.jpg.webp">
        <div class="next_post_title p-[5px]">
          <p class="font-bold text-gray-400 text-[11px] text-center">
            Bài viết kế tiếp
            <swap-right-outlined/>
          </p>
          <a href="https://thepte.com/pte-mock-test-1/">PTE Mock Test 1</a>
        </div>
      </div>
    </div>

    <div class="max-w-[400px] m-auto mt-[50px] text-center rounded py-[20px]" style="border: 1px solid gainsboro">

      <h3 class="font-bold">Đăng ký ngay</h3>
      <ContactForm />
    </div>

  </div>
</template>

<script setup>
import {
  SwapLeftOutlined,
  SwapRightOutlined
} from "@ant-design/icons-vue";

const tagColors = [
  "orange",
  "pink",
  "green",
  "cyan",
  "blue",
  "purple",
  "#108ee9",
  "#f50",
  "#2db7f5",
  "#87d068",
  "default",
];

const postData = {
  content: '<!-- wp:paragraph -->\n<p>Kadokawa đã ra mắt video quảng cáo đầy đủ phụ đề tiếng Anh đầu tiên và hình ảnh teaser thứ hai (ở phiên bản hiển thị và vô hình) cho anime truyền hình của manga hài kinh dị Mieruko-chan của Tomoki Izumi vào thứ Sáu. Video công bố dàn diễn viên lồng tiếng chính của anime, các nhân viên bổ sung và buổi ra mắt vào tháng 10, đồng thời nó cũng tiết lộ và xem trước bài hát chủ đề mở đầu của anime.</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:image {"align":"center"} -->\n<div class="wp-block-image"><figure class="aligncenter"><img src="https://cdn.animenewsnetwork.com/thumbnails/fit750x750/cms/news.4/175190/vis-on.png.jpg" alt=""/></figure></div>\n<!-- /wp:image -->\n\n<!-- wp:image {"align":"center"} -->\n<div class="wp-block-image"><figure class="aligncenter"><img src="https://cdn.animenewsnetwork.com/thumbnails/fit750x750/cms/news.4/175190/vis-off.png.jpg" alt=""/></figure></div>\n<!-- /wp:image -->\n\n<!-- wp:paragraph -->\n<p>Các thành viên của dàn diễn viên là:</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:paragraph {"align":"center"} -->\n<p class="has-text-align-center">Sora Amamiya&nbsp;trong vai Miko Yotsuya</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:image {"align":"center"} -->\n<div class="wp-block-image"><figure class="aligncenter"><img src="https://cdn.animenewsnetwork.com/thumbnails/fit750x750/cms/news.4/175190/mierukocyan_miko_web.jpg.jpeg" alt="anime Mieruko-chan" title="anime Mieruko-chan"/></figure></div>\n<!-- /wp:image -->\n\n<!-- wp:paragraph {"align":"center"} -->\n<p class="has-text-align-center">Kaede Hondo&nbsp;trong vai Hana Yurikawa, best friend của Miko</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:image {"align":"center"} -->\n<div class="wp-block-image"><figure class="aligncenter"><img src="https://cdn.animenewsnetwork.com/thumbnails/fit750x750/cms/news.4/175190/mierukocyan_hana_web.jpg.jpeg" alt="anime Mieruko-chan" title="anime Mieruko-chan"/></figure></div>\n<!-- /wp:image -->\n\n<!-- wp:paragraph {"align":"center"} -->\n<p class="has-text-align-center">Ayane Sakura&nbsp;trong vai Yulia Nikaidō, bạn cùng lớp của Miko và Hana</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:image {"align":"center"} -->\n<div class="wp-block-image"><figure class="aligncenter"><img src="https://cdn.animenewsnetwork.com/thumbnails/fit750x750/cms/news.4/175190/mierukocyan_yuria_web.jpg.jpeg" alt="anime Mieruko-chan" title="anime Mieruko-chan"/></figure></div>\n<!-- /wp:image -->\n\n<!-- wp:paragraph -->\n<p>Amamiya hát bài hát chủ đề mở đầu "Mienai Kara ne !?" (Vì bạn không thể nhìn thấy chúng, phải không !?)</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:paragraph -->\n<p>Takahiro Majima (Interspecies Reviewers) và Shintarō Matsushima lần lượt là trợ lý đạo diễn và trợ lý chỉ đạo. Kana Utatane (RE-MAIN) đang soạn nhạc. Các nhân viên mới được công bố khác bao gồm:</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:list -->\n<ul><li>Thiết kế nhân vật phụ:&nbsp;Kyoko Kametani.&nbsp;Futoshi Chikkyo, Tin</li><li>Thiết kế quái vật:&nbsp;Makoto Uno&nbsp;(High School DxD Hero,&nbsp;Interspecies Reviewers),&nbsp;Yasuhiro Moriki,&nbsp;Futoshi Chikkyo,&nbsp;Katsuzo Hirata,&nbsp;Hiroya Iijima,&nbsp;Hiroyasu Oda&nbsp;(studio Mogana)</li><li>Thiết kế đề xuất:&nbsp;Yukinori Umetsu</li><li>Thiết kế trang phục:&nbsp;Yuka Takashina</li><li>Giám đốc phim:&nbsp;Masahide Yanagisawa,&nbsp;Hideki Hashimoto,&nbsp;Katsuzo Hirata,&nbsp;Kyoko Kametani,&nbsp;Yuka Takashina</li><li>Biên tập viên:&nbsp;Ayako Tan</li><li>Nghệ sĩ khóa màu:&nbsp;Ritsuko Utagawa</li><li>Thiết kế mỹ thuật:&nbsp;Midori Iwasawa&nbsp;(Kusanagi),&nbsp;Shin Watanabe&nbsp;(EKACHI EPILKA)</li><li>Giám đốc nghệ thuật:&nbsp;Ayano Okamoto</li><li>Khái niệm tổng hợp:&nbsp;Junpei Takatsu</li><li>Giám đốc Nhiếp ảnh:&nbsp;Hyo Mok Yang</li><li>Sản xuất âm nhạc:&nbsp;Kadokawa</li><li>Giám đốc âm thanh:&nbsp;Fumiyuki Go</li><li>Hiệu ứng âm thanh:&nbsp;Maki Takuma</li><li>Sản xuất âm thanh:&nbsp;Magic Capsule</li></ul>\n<!-- /wp:list -->\n\n<!-- wp:paragraph -->\n<p>Bộ phim sẽ ra mắt vào tháng 10 trên Tokyo MX, BS NTV, AT-X và các kênh khác. Kênh YouTube của Kadokawa sẽ tổ chức một chương trình đặc biệt với dàn diễn viên vào ngày 28 tháng 7.</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:image {"align":"center"} -->\n<div class="wp-block-image"><figure class="aligncenter"><img src="https://cdn.animenewsnetwork.com/thumbnails/max700x700/cms/news.4/170746/visual.jpg" alt="anime Mieruko-chan" title="anime Mieruko-chan"/></figure></div>\n<!-- /wp:image -->\n\n<!-- wp:paragraph -->\n<p>Yen Press xuất bản manga bằng tiếng Anh và nó mô tả câu chuyện:</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:image {"align":"right"} -->\n<div class="wp-block-image"><figure class="alignright"><img src="https://cdn.animenewsnetwork.com/thumbnails/max400x400/cms/news.4/170746/manga.jpg" alt="anime Mieruko-chan" title="anime Mieruko-chan"/></figure></div>\n<!-- /wp:image -->\n\n<!-- wp:quote -->\n<blockquote class="wp-block-quote"><p>Một ngày nọ, Miko đột nhiên bắt đầu nhìn thấy những sinh vật kỳ dị mà những người khác không thể. Phản ứng của cô ấy là không chạy, không phải đối mặt với họ, mà là làm mọi cách để hoàn toàn phớt lờ họ! Liệu cô có thể giữ một khuôn mặt thẳng thắn và tiếp tục cuộc sống hàng ngày của mình trong khi bị bao vây bởi những con quái vật kinh hoàng?</p></blockquote>\n<!-- /wp:quote -->\n\n<!-- wp:paragraph -->\n<p>Yuki Ogawa (FLCL Progressive, Miru Tights, Interspecies Reviewers) sẽ đạo diễn anime tại Passione. Kenta Ihara (Saga of Tanya the Evil, Cautious Hero, Shachibato! President, It\'s Time for Battle!) Sẽ giám sát và viết kịch bản cho loạt phim. Chikashi Kadekaru (Juni Taisen: Zodiac War, For Whom the Alchemist Exists) sẽ thiết kế các nhân vật, đồng thời cũng là đạo diễn hoạt hình chính. Makoto Uno (High School DxD Hero, Interspecies Reviewers) đang thiết kế những con quái vật.</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:paragraph -->\n<p>Izumi đã ra mắt manga trên trang web ComicWalker của Kadokawa vào tháng 11 năm 2018, và Kadokawa đã xuất bản tập thứ năm của manga vào ngày 22 tháng 3. Yen Press đã xuất bản tập thứ hai của manga vào ngày 23 tháng 2.</p>\n<!-- /wp:paragraph -->\n\n<!-- wp:paragraph -->\n<p><em>Sources:&nbsp;Mieruko-chan&nbsp;anime\'s&nbsp;<a rel="noreferrer noopener" href="https://mierukochan.jp/" target="_blank">website</a>,&nbsp;<a rel="noreferrer noopener" href="https://natalie.mu/comic/news/437161" target="_blank">Comic </a></em>Natalie, animenewsnetwork.</p>\n<!-- /wp:paragraph -->',
  postTags: [
    {__typename: "Tag", name: "anime mới", slug: "anime-moi"},
    {
      __typename: "Tag",
      name: "anime kinh dị",
      slug: "anime-kinh-di",
    },
    {
      __typename: "Tag",
      name: "anime sắp ra mắt",
      slug: "anime-sap-ra-mat",
    },
    {
      __typename: "Tag",
      name: "anime ra mắt tháng 10 năm 2021",
      slug: "anime-ra-mat-thang-10-nam-2021",
    },
    {
      __typename: "Tag",
      name: "Mieruko-chan Comedy",
      slug: "mieruko-chan-comedy",
    },
  ]
}

</script>

<style>

</style>
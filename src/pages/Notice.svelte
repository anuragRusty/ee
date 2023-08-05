<!-- NoticePage.svelte -->
<script>
     import { slide,scale } from "svelte/transition";
    const notices = [
      {
        title: 'Notice 1',
        content: 'This is the content of Notice 1...',
        date: 'August 4, 2023',
      },
      {
        title: 'Notice 2',
        content: 'This is the content of Notice 2...',
        date: 'August 3, 2023',
      },
    ];
  </script>
  
  <div class="container" in:slide>
    {#each notices as notice}
      <div transition:scale class="notice-box">
        <h1>{notice.title}</h1>
        <p>{notice.content}</p>
        <small>Published on: {notice.date}</small>
      </div>
    {/each}
    </div>
  
  <style>
    .container {
      display:flex;
      width:100%;
      gap: 10px;
      padding-bottom: 10px;
    }
  
    .notice-box {
      width:calc(50% - 10px);
      background-color: #f8f8f8;
      padding: 20px 20px 20px 20px;
      border-radius: 8px;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    }
  
    h1 {
      font-size: 30px;
      margin-bottom: 10px;
      color: #333;
    }
  
    p {
      font-size: 16px;
      margin-bottom: 20px;
      color: #555;
    }
  
    small {
      font-size: 12px;
      color: #888;
    }

    @media (max-width: 768px) {
        .container{
            flex-direction: column;
        }

        .notice-box{
            width:calc(100% - 40px);
        }
    }
  </style>
  
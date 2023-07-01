<script>
  let advice = "";
  let id = "";
  const generateAdvice = async () => {
    const n = Math.floor(Math.random() * 200);
    const data = await fetch(`https://api.adviceslip.com/advice/${n}`);
    const response = await data.json();
    id = response.slip.id;
    advice = response.slip.advice;
  };
  generateAdvice();
</script>

<span
  class="text-white bg-[#1f2632] w-full items-center justify-center p-[1rem] flex min-h-[100vh] h-full"
>
  <span
    class="relative justify-evenly w-full max-w-[35rem] bg-[#323a49] h-max px-[1.2rem] py-[5rem] flex flex-col items-center rounded-[1rem] gap-[2rem]"
  >
    <p class="text-[#52ffa8] text-[1.1rem]">ADVICE #{id}</p>

    <span id="advice" class="text-center text-[1.3rem] font-semibold"
      >{advice}</span
    >

    <span class="hidden md:flex lg:flex"
      ><svg width="444" height="16" xmlns="http://www.w3.org/2000/svg"
        ><g fill="none" fill-rule="evenodd"
          ><path fill="#4F5D74" d="M0 8h196v1H0zM248 8h196v1H248z" /><g
            transform="translate(212)"
            fill="#CEE3E9"
            ><rect width="6" height="16" rx="3" /><rect
              x="14"
              width="6"
              height="16"
              rx="3"
            /></g
          ></g
        ></svg
      ></span
    >
    <span class="flex md:hidden lg:hidden"
      ><svg width="295" height="16" xmlns="http://www.w3.org/2000/svg"
        ><g fill="none" fill-rule="evenodd"
          ><path fill="#4F5D74" d="M0 8h122v1H0zM173 8h122v1H173z" /><g
            transform="translate(138)"
            fill="#CEE3E9"
            ><rect width="6" height="16" rx="3" /><rect
              x="14"
              width="6"
              height="16"
              rx="3"
            /></g
          ></g
        ></svg
      ></span
    >
    <span
      on:click={generateAdvice}
      class="ease-in -translate-y-1/2 duration-100 hover:shadow-[0_0px_20px_rgba(82,255,_168,_0.7)] absolute bg-[#52ffa8] cursor-pointer top-[100%] p-[1rem] rounded-full"
      ><svg width="24" height="24" xmlns="http://www.w3.org/2000/svg"
        ><path
          d="M20 0H4a4.005 4.005 0 0 0-4 4v16a4.005 4.005 0 0 0 4 4h16a4.005 4.005 0 0 0 4-4V4a4.005 4.005 0 0 0-4-4ZM7.5 18a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Zm0-9a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Zm4.5 4.5a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Zm4.5 4.5a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Zm0-9a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Z"
          fill="#202733"
        /></svg
      ></span
    >
  </span>
</span>

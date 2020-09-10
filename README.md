# Fouita (svelte + tailwind) Avatar component

Simple Avatar component that you can customize whatever you like with tailwind classes!

# install

```bash
    $npm i @fouita/avatar
```

# Usage

## Simple usage

![avatar custom](https://cdn.fouita.com/assets/pics/template/avatar/avatar-simple.png)

```html
<script>
	import Avatar from '@fouita/avatar'
</script>

<div class="flex justify-center">

	<Avatar src="https://randomuser.me/api/portraits/men/62.jpg" size=12 />
	<Avatar src="https://randomuser.me/api/portraits/women/68.jpg" size=12 />
	<Avatar size=12 />
	<Avatar size=12 bg="red-600" >BA</Avatar>
		
</div>
```


## Avatar Group

Use the avatar in a group like the following

![avatar custom](https://cdn.fouita.com/assets/pics/template/avatar/avatar-grp.png)

```html
<script>
	import Avatar from '@fouita/avatar'
	
	const base_url = "https://randomuser.me/api/portraits/"
	
	let imgs = [
		{src: 'women/13.jpg', name: 'w_13'},
		{src: 'women/25.jpg', name: 'w_25'},
		{src: 'men/34.jpg', name: 'men_34'},
		{src: 'women/35.jpg', name: 'w_35'},
		{src: 'men/48.jpg', name: 'men_48'}
	]
	
	let klass = '-ml-4 rounded-full border-r-2 border-white'
</script>

<div class="flex flex-row-reverse justify-center">

	<Avatar class="{klass} text-base text-white" size="10" bg="gray-500" >
		+5
	</Avatar>
	{#each imgs as img}
		<Avatar class="{klass}" size="10" src={base_url+img.src} alt={img.name} bg="white" />		
	{/each}

</div>
```


## Avatar badge

Add custom color badges to the avatar

![avatar custom](https://cdn.fouita.com/assets/pics/template/avatar/avatar-badge.png)

```html

<script>
	import Avatar from '@fouita/avatar'					
	let badge_class = 'rounded-full w-3 h-3 absolute bottom-0 right-0'
	
</script>

<div class="flex justify-center">

	<Avatar src="https://randomuser.me/api/portraits/men/62.jpg" size=12>
		<div slot="badge" class="bg-green-500 {badge_class}" key="k2">
		</div>
	</Avatar>	

	<Avatar src="https://randomuser.me/api/portraits/women/68.jpg" size=12>
		<div slot="badge" class="bg-red-500 {badge_class}" key="k3">
		</div>
	</Avatar>	

	<Avatar src="https://randomuser.me/api/portraits/women/75.jpg" size=12>
		<div slot="badge" class="bg-orange-500 {badge_class}" key="k4">
		</div>
	</Avatar>	

</div>
```

## Avatar round

Avatar custom round example

![avatar custom](https://cdn.fouita.com/assets/pics/template/avatar/avatar-round.png)

```html
<script>
	import Avatar from '@fouita/avatar'
</script>

<div class="flex justify-center">

	<Avatar class="rounded-none text-white text-xl"  />
	<Avatar class="rounded-sm text-white text-xl"  />
	<Avatar class="rounded text-white text-xl"  />
	<Avatar class="rounded-lg text-white text-xl"  />
	<Avatar class="rounded-full text-white text-xl"  />
	
</div>
```

## Avatar size

Custom size for your avatar based on tailwind size scale

![avatar custom](https://cdn.fouita.com/assets/pics/template/avatar/avatar-size.png)

```html
<script>
	import Avatar from '@fouita/avatar'
	let src = 'https://randomuser.me/api/portraits/women/68.jpg'
</script>

<div class="flex justify-center" key="k1">
	<Avatar size="8" {src} />
	<Avatar size="10" {src} />
	<Avatar size="12" {src} />
	<Avatar size="16" {src} />
	<Avatar size="20" {src} />
</div>
```



## Custom text, icon

Custom text/icon you can use

![avatar custom](https://cdn.fouita.com/assets/pics/template/avatar/avatar-custom.png)

```html
<script>
	import Avatar from '@fouita/avatar'
	import {MailIcon} from 'svelte-feather-icons'
</script>

<div class="flex justify-center">
	
	<Avatar alt="User Name"  size=12/>
	<Avatar alt="First Last" bg="green-500" size=12 />
	<Avatar bg="purple-500" size=12>
		XY
	</Avatar>
	<Avatar bg="pink-500" size=12>
		<MailIcon class="w-8" />
	</Avatar>
		
</div>
```


## About

[Fouita : UI framework for svelte + tailwind components](fouita.com)
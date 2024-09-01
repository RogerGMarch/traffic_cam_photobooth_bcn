# Repo for Traffic-Cam-Photobooth-bcn.pages.dev


## Contributing:
I'm happy to accept PRs for this project, here are some basic guidelines for doing so.

Here is the basic stuff to keep in mind:

- *Static Site*: In general, the site is completely static. It does not have a server, nor do I want to run one. Everything served on the site needs to be already accessible online from a simple GET request. As it stands now, the way images update is just by refreshing the `src` attribute of `<img>` tags.

- *Camera Data*: All cameras should be passed in one big object where they are used. If you see a significant performance drop, you can separate out the allCameras object into a separate js file, but the user's device will be responsible for processing that entire list one way or another. This allows the site to find the cameras nearest to the user without their location leaving their device, which is important for user privacy. Every camera needs (at the very least): a name, lat/long coordinates, and an image URL for their feed, following the existing cameras in allCameras. Also, camera IDs are passed via URL parameters from one page to another. Keep this pattern.

- *Camera Update Speed*: Slowly updating cameras are not a good experience for the user, and I do not want to create a site that encourages people to stand in the street for minutes at a time. With a PR, please provide how often the images (or video) from the cameras will update. Any image refresh rate slower than 15s is probably not worth putting on. 

I understand that these place some restrictions on which cities can reasonably be added. For a project like this, a free site that always works well and can live forever is better than one with more features that costs money and needs to be maintained.

Other than that, go wild. Just fork it, build it out, and submit :)